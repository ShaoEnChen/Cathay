<template>
	<b-container fluid :id="`club${count}`" class="no-padding">
		<b-row class="my-1">
			<b-col md="4">
				<b-form-group
					label="社團經歷"
					:label-for="`clubName${count}`">
					<b-form-input type="text" :id="`clubName${count}`"
						:name="`clubName${count}`"
						placeholder="請輸入社團名稱">
					</b-form-input>
				</b-form-group>
			</b-col>
			<b-col md="4">
				<b-form-group
					label="擔任職務"
					:label-for="`cposition${count}`">
					<b-form-input type="text" :id="`cposition${count}`"
						:name="`cposition${count}`"
						placeholder="e.g. 副社長">
					</b-form-input>
				</b-form-group>
			</b-col>
		</b-row>
		<b-row class="my-1">
			<b-col md="4" lg="3">
				<b-form-group class="no-padding"
					label="服務期間"
					:label-for="`csyear${count}`">
					<b-input-group prepend="從" append="年">
						<b-form-select :id="`csyear${count}`"
							:name="`csyear${count}`"
							:options="years">
						</b-form-select>
					</b-input-group>
				</b-form-group>
			</b-col>
			<b-col md="3" lg="2">
				<b-input-group append="月">
					<b-form-select :id="`csmonth${count}`"
						:name="`csmonth${count}`"
						:options="months">
					</b-form-select>
				</b-input-group>
			</b-col>
		</b-row>
		<b-row class="mt-1 mb-4">
			<b-col md="4" lg="3">
				<b-input-group prepend="到" append="年">
					<b-form-select :id="`ceyear${count}`"
						:name="`ceyear${count}`"
						:options="years">
					</b-form-select>
				</b-input-group>
			</b-col>
			<b-col md="3" lg="2">
				<b-input-group append="月">
					<b-form-select :id="`cemonth${count}`"
						:name="`cemonth${count}`"
						:options="months">
					</b-form-select>
				</b-input-group>
			</b-col>
		</b-row>
	</b-container>
</template>

<script>
export default {
	props: {
		years: Array,
		months: Array,
		count: String
	}
}
</script>

<style lang="sass" scoped>
	.input-group-prepend > .input-group-text
		padding: 0.375rem 0.75rem 0.375rem 0;

	@include media-breakpoint-up(md)
		[id^=csmonth],
		[id^=csmonth] + .input-group-append
			margin-top: 1.875rem

	@include media-breakpoint-down(sm)
		[id^=csmonth],
		[id^=csmonth] + .input-group-append
			margin-bottom: 1rem

		[id^=cemonth],
		[id^=cemonth] + .input-group-append
			margin-top: 1rem

		[id^=csmonth],
		[id^=cemonth]
			margin-left: 1.75rem
</style>
