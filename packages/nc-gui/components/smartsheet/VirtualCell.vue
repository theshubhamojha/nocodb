<script setup lang="ts">
import type { ColumnType } from 'nocodb-sdk'
import { ActiveCellInj, CellValueInj, ColumnInj, RowInj, provide, toRef, useVirtualCell } from '#imports'
import type { Row } from '~/lib'
import { NavigateDir } from '~/lib'

const props = defineProps<{
  column: ColumnType
  modelValue: any
  row: Row
  active?: boolean
}>()

const emit = defineEmits(['update:modelValue', 'navigate'])

const column = toRef(props, 'column')
const active = toRef(props, 'active', false)
const row = toRef(props, 'row')

provide(ColumnInj, column)
provide(ActiveCellInj, active)
provide(RowInj, row)
provide(CellValueInj, toRef(props, 'modelValue'))

const { isLookup, isBt, isRollup, isMm, isHm, isFormula, isCount } = useVirtualCell(column)
</script>

<template>
  <div
    class="nc-virtual-cell w-full"
    @keydown.stop.enter.exact="emit('navigate', NavigateDir.NEXT)"
    @keydown.stop.shift.enter.exact="emit('navigate', NavigateDir.PREV)"
  >
    <LazyVirtualCellHasMany v-if="isHm" />
    <LazyVirtualCellManyToMany v-else-if="isMm" />
    <LazyVirtualCellBelongsTo v-else-if="isBt" />
    <LazyVirtualCellRollup v-else-if="isRollup" />
    <LazyVirtualCellFormula v-else-if="isFormula" />
    <LazyVirtualCellCount v-else-if="isCount" />
    <LazyVirtualCellLookup v-else-if="isLookup" />
  </div>
</template>
