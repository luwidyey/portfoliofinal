<footer
  id="foot"
  class="py-20 sm:py-32 bg-black border-t border-solid border-white flex flex-col gap-4 sm:gap-8 justify-center items-center"
>
  <script>
    async function handleSubmit(event) {
      event.preventDefault();

      const form = event.target;
      const formData = new FormData(form);

      const response = await fetch("https://formspree.io/f/mjkvrrpw", {
        method: "POST",
        body: formData,
        headers: {
          Accept: "application/json",
        },
      });

      if (response.ok) {
        form.reset();
        alert("Message sent successfully!");
      } else {
        alert("There was an error. Please try again.");
      }
    }
  </script>

  <form on:submit={handleSubmit} class="flex flex-col gap-4 w-full max-w-md">
    <h3
      class="flex items-center justify-center font-semibold text-3xl sm:text-4xl md:text-5xl"
    >
      <span class="poppins text-white-0">CONTACT ME</span>
    </h3>
    <input
      type="text"
      name="name"
      placeholder="Name"
      required
      class="w-full p-3 bg-gray-800 text-white border border-gray-600 rounded-md outline-none focus:border-gray-400"
    />
    <input
      type="email"
      name="email"
      placeholder="Email"
      required
      class="w-full p-3 bg-gray-800 text-white border border-gray-600 rounded-md outline-none focus:border-gray-400"
    />
    <textarea
      name="message"
      placeholder="Message"
      rows="4"
      required
      class="w-full p-3 bg-gray-800 text-white border border-gray-600 rounded-md outline-none focus:border-gray-400"
    ></textarea>
    <button
      type="submit"
      class="w-full p-3 mt-4 bg-red-950 text-white font-medium rounded-md hover:bg-red-600 transition-colors duration-200"
    >
      Send Message
    </button>
  </form>

  <div class="flex flex-col items-center justify-center">
    <div
      class="flex items-center gap-4 sm:gap-6 text-2xl sm:text-3xl md:text-4xl mx-auto"
    >
      <a
        href="https://www.facebook.com/luwiyyyy"
        target="_blank"
        class="text-white duration-200 hover:text-gray-700"
        aria-label="Facebook"
      >
        <i class="fa-brands fa-square-facebook"></i>
      </a>
    </div>

    <h1 class="items-center justify-center mt-20">All rights reserved.</h1>
  </div>
</footer>
