<script setup>
	import { ref } from "vue"

	const formName = "book-a-demo-form"
	const isProcessing = ref(false)
	let form = ref({
		first_name: "",
		last_name: "",
		company: "",
		contact_number: "",
		email_address: "",
		email_subject: "",
		email_content: "",
	})

	function handleFormSubmit() {
		console.error("sending...")
	}
</script>

<template>
	<section class="contact-form [ py-20 ] [ bg-primary ]">
		<div class="[ px-6 mx-auto ] [ container ]">
			<div class="[ flex flex-wrap gap-10 ]">
				<div class="[ grid ] [ w-full md:w-1/3 ]">
					<h2 class="[ font-bold ]">Book your demo today</h2>
					<p class="[ mt-12 ]">
						“Kudosity was the easiest and most effective marketing tool we’ve
						ever used for lead qualification at Uber.”
					</p>

					<span class="[ mt-6 ]">Uber, Singapore</span>

					{{ form }}
				</div>

				<div>
					<form
						action=""
						@submit.prevent="handleFormSubmit">
						<div>
							<div>
								<label :for="`${formName}-input-first-name`">First name</label>
								<Input
									v-model="form.first_name"
									:id="`${formName}-input-first-name`"
									look="line"
									placeholder="First name"
									class="input-custom-focus-visible" />
							</div>

							<div>
								<label :for="`${formName}-input-last-name`">Last name</label>
								<Input
									v-model="form.last_name"
									:id="`${formName}-input-last-name`"
									look="line"
									placeholder="Last name"
									class="input-custom-focus-visible" />
							</div>
						</div>

						<div>
							<div>
								<label :for="`${formName}-input-company`">Company</label>
								<Input
									v-model="form.company"
									:id="`${formName}-input-company`"
									look="line"
									placeholder="Company"
									class="input-custom-focus-visible" />
							</div>

							<div>
								<label :for="`${formName}-input-contact-number`">
									Phone number
								</label>
								<Input
									v-model="form.contact_number"
									:id="`${formName}-input-contact-number`"
									look="line"
									placeholder="Phone number"
									class="input-custom-focus-visible" />
							</div>
						</div>

						<div>
							<div>
								<label :for="`${formName}-input-email`">Email address</label>
								<Input
									v-model="form.email_address"
									:id="`${formName}-input-email`"
									look="line"
									placeholder="Email address"
									class="input-custom-focus-visible" />
							</div>
						</div>

						<div>
							<div>
								<label :for="`${formName}-input-email-subject`">Subject</label>
								<Input
									v-model="form.email_subject"
									:id="`${formName}-input-email-subject`"
									look="line"
									placeholder="Subject"
									class="input-custom-focus-visible" />
							</div>
						</div>

						<div>
							<div>
								<label :for="`${formName}-input-email-content`">Message</label>
								<textarea
									v-model="form.email_content"
									:id="`${formName}-input-email-content`"
									placeholder="Message"
									class="input-custom-focus-visible" />
							</div>
						</div>

						<Button
							type="submit"
							look="primary"
							:disabled="isProcessing">
							Submit Request
						</Button>
					</form>
				</div>
			</div>
		</div>
	</section>
</template>

<style lang="postcss">
	.input-custom-focus-visible {
		@apply focus-visible:ring-offset-primary;
	}
</style>