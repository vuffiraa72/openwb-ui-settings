<template>
	<div class="device-sungrow-counter">
		<openwb-base-heading>
			Einstellungen für Sungrow Zähler
			<span class="small">(Modul: {{ $options.name }})</span>
		</openwb-base-heading>
		<openwb-base-button-group-input
			title="Version"
			:buttons="[
				{ buttonValue: 0, text: 'SH (Hybrid)' },
				{ buttonValue: 1, text: 'SG (kein Hybrid)' },
			]"
			:model-value="configuration.version"
			@update:model-value="
				updateConfiguration($event, 'configuration.version')
			"
		/>
	</div>
</template>

<script>
export default {
	name: "DeviceSungrowCounter",
	emits: ["update:configuration"],
	props: {
		configuration: { type: Object, required: true },
		deviceId: { default: undefined },
		componentId: { required: true },
	},
	methods: {
		updateConfiguration(event, path = undefined) {
			this.$emit("update:configuration", { value: event, object: path });
		},
	},
};
</script>
