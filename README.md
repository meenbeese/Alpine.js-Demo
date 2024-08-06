# Alpine.js Demo Repository

This repository contains a simple example to showcase the capabilities of Alpine.js by extending the functionality of HTML.

<img src="./demo.png" alt="Demo">

## Technologies Used

- HTML
- Alpine.js
- Tailwind CSS

## Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/meenbeese/Alpine.js-Demo.git
   ```
2. Navigate to the project directory:
   ```bash
   cd alpinejs-demo/src
   ```
3. Open the `index.html` file in your web browser.

## Usage

The example demonstrates how to use Alpine.js stores to manage state and toggle dark mode using only minimal inline JS.

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <script src="https://unpkg.com/alpinejs" defer></script>
    <script src="https://cdn.tailwindcss.com"></script>
    <title>Alpine.js Stores</title>
  </head>
  <body>
    <div
      x-data
      :class="$store.darkMode.on && 'bg-gray-800 text-white'"
      class="container mx-auto max-w-sm mt-6 bg-gray-50 p-4"
    >
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis
      doloremque facere asperiores consequuntur amet molestias dolorem accusamus
      voluptas voluptatibus aliquid, quia laboriosam est animi velit.
      Perferendis, nihil cumque laborum repellendus repudiandae perspiciatis hic
      a vitae odit ut velit tempore pariatur.

      <button
        @click="$store.darkMode.toggle()"
        :class="$store.darkMode.on && 'bg-gray-700'"
        class="block mt-4 text-xs bg-gray-200 px-4 py-2"
      >
        Toggle Dark Mode
      </button>
    </div>

    <script>
      document.addEventListener("alpine:init", () => {
        Alpine.store("darkMode", {
          on: false,

          toggle() {
            this.on = !this.on;
          },
        });
      });
    </script>
  </body>
</html>
```

## License

This project is licensed under the MIT License.
