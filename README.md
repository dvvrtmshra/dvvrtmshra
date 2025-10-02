# Hi, I'm **Dev Vrat** 👋

**Sort of likes computers and maths**. Always learning. 🐈

---


cpp
#include "t.hpp"
#include <iostream>
#include <cmath> // Include cmath for M_PI

using namespace t;

int main() {
  auto box = Box(1, 1, 1);
  auto material = NormalColor();
  auto mesh = Mesh(box, material);

  const auto width = 80;
  const auto height = 24;

  auto scene = Scene();
  auto camera = PerspectiveCamera(M_PI / 4, static_cast<double>(width) / height,
                                  0.01, 10);
  camera.translate(0, 0, 1);

  scene.add(mesh);
  scene.add(camera);

  auto renderer = Rasterizer();
  auto renderTarget =
      RenderTarget<double>(width, height, TextureFormat::RgbDouble);

  while (true) {
    // Rotation for animation
    mesh.localRotation.x += 0.002;
    mesh.localRotation.y += 0.001;

  renderer.render(scene, camera, renderTarget);

  std::cout << "\x1b[H"; // Set terminal's cursor position to top-left corner

  for (int j = 0; j < renderTarget.height; j++) {
      for (int i = renderTarget.width - 1; i > -1; i--) {
        int index = (i + j * renderTarget.width) * 3;

   auto r = renderTarget.texture.image[index];
        auto g = renderTarget.texture.image[index + 1];
        auto b = renderTarget.texture.image[index + 2];

  // Print pixel using 24-bit ANSI True Color
        std::cout << "\033[38;2;" << static_cast<int>(r * 255) << ";"
                  << static_cast<int>(g * 255) << ";"
                  << static_cast<int>(b * 255) << "m@\033[0m";
      }
      std::cout << "\n";
    }
  }
}

## 💻 Skills

### Programming languages
![BASH](https://img.shields.io/badge/BASH-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white)
![C](https://img.shields.io/badge/C-03599C?style=for-the-badge&logo=c&logoColor=white)
![JAVA](https://img.shields.io/badge/Java-007396?style=for-the-badge&logo=java&logoColor=white)
![JAVASCRIPT](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![PYTHON](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)


### Web dev
![MONGODB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![NEXT.JS](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)

---

## 🛠️ Software
![ANDROID STUDIO](https://img.shields.io/badge/Android_Studio-3DDC84?style=for-the-badge&logo=android-studio&logoColor=white)
![BLENDER](https://img.shields.io/badge/Blender-F5792A?style=for-the-badge&logo=blender&logoColor=white)


---

## ✨ Other things

* **Favorite programming language:** Python.
* **Favorite technology:** Blockchain.
* **Interests:** Swimming, Arts.

---

## 🔗 Find Me Online
*You can find links to all my work and social profiles here:*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](YOUR_LINKEDIN_URL)
[![X (Twitter)](https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white)](YOUR_TWITTER_URL)
