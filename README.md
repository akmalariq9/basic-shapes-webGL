# **Basic Shapes (2D and 3D) - webGL**

<div align=justify>

Berikut adalah Repository untuk pengerjaan Tugas 3 mata kuliah Grafika Komputer (Membuat _basic shapes_ menggunakan webGL) yang berisi _source code_, dokumentasi atau penjelasan, dan _screenshot output_.

# **Identitas**

| Nama                | NRP        | Kelas              |
| ------------------- | ---------- | ------------------ |
| Akmal Ariq Romadhon | 5025211188 | Grafika Komputer A |

# **2D Square**

Berikut adalah dokumentasi serta _screenshot output_ dari code yang ada untuk pembuatan persegi menggunakan 2 segitiga.

## **Penjelasan**

_coming soon_

## **_Screenshot Ouput_**
_coming soon_

# **3D Cube**

Berikut adalah dokumentasi serta _screenshot output_ dari code yang ada untuk pembuatan persegi menggunakan 2 segitiga.

## **Penjelasan**

Fungsi `draw` di _code_ 3D-Cube terdiri dari 3 bagian utama, yaitu deklarasi _mode_, pemilihan warna, dan pengaturan posisi.

```c++
function draw() {
    gl.clearColor(0, 0, 0, 1);
    gl.clear(gl.COLOR_BUFFER_BIT | gl.DEPTH_BUFFER_BIT);

    /* Draw the six faces of a cube, with different colors. */

    // drawPrimitive( gl.TRIANGLE_FAN, [1,1,0,1], [ -0.5,-0.5,-0.5, -0.5,0.3,-0.5, 0.3,0.3,-0.5, 0.3,-0.5,-0.5 ]);    //Front side
        drawPrimitive(
          gl.TRIANGLE_FAN,
          [1, 1, 1, 1],
          [-0.5, 0.3, 0.5, -0.3, 0.5, 0.5, 0.5, 0.5, -0.5, 0.3, 0.3, -0.5]
        ); //Top face
        drawPrimitive(
          gl.TRIANGLE_FAN,
          [1, 0, 1, 0.5],
          [0.3, -0.5, -0.5, 0.3, 0.3, -0.5, 0.5, 0.5, -0.5, 0.5, -0.3, -0.5]
        ); //Right Face
        drawPrimitive(
          gl.TRIANGLE_FAN,
          [1, 0.5, 0, 5],
          [-0.5, -0.5, 0.5, -0.3, -0.3, -0.5, 0.5, -0.3, -0.3, 0.3, -0.5, -0.5]
        ); //Bottom Face
        drawPrimitive(
          gl.TRIANGLE_FAN,
          [0.1, 0, 1, 0.5],
          [-0.5, -0.5, 0.5, -0.3, -0.3, 0.5, -0.3, 0.5, 0.5, -0.5, 0.3, 0.5]
        ); //Left  Face
        drawPrimitive(
          gl.TRIANGLE_FAN,
          [0, 1, 0.3, 0.5],
          [0.5, -0.3, 0.5, -0.3, -0.3, 0.5, -0.3, 0.5, 0.5, 0.5, 0.5, 0.5]
        ); // Back Face
      }
```
_Primive Type_ (primitiveType) merupakan argumen pertama yang menentukan _mode_ untuk menggambar objek. Dalam kode tersebut, digunakan _primitive type_ `gl.TRIANGLE_FAN`, yang berarti objek akan digambar menggunakan segitiga-segitiga.

Warna (colors) merupakan argumen kedua adalah _array_ yang berisi informasi tentang warna atau atribut tertentu untuk setiap titik dalam objek. Dengan argumen ini, objek yang digambar dapat memiliki warna sesuai angka dalam _array_, misalnya `[1, 1, 1, 1]` berarti warna putih dengan tingkat _opacity_ penuh.

Koordinat Titik (vertices) merupakan arguman ketiga yang merupaka _array _ dengan fungsi untuk menentukan koordinat titik-titik dalam objek. Setiap tiga koordinat berturut-turut akan membentuk sebuah segitiga. Dalam konteks objek tiga dimensi, angka tersebut akan menggambarkan sudut-sudut segitiga yang akan membentuk wajah objek tersebut.

Fungsi _drawPrimitive_ ini dipanggil beberapa kali untuk membuat sisi dari masing masing sisi kubus, yaitu sisi depan, belakang, atas, bawah, kanan, dan kiri.

## **_Screenshot Ouput_**
Berikut adalah _Screenshot output_ dari code tersebut:

- **Kubus Awal (Tampak dari depan)**

![Kubus1](https://cdn.discordapp.com/attachments/1150687865420906517/1158463136454684742/Screenshot_981.png?ex=651c565e&is=651b04de&hm=51b77b926a792534ad2d8027a6fc85eed27d1df19c88ca3840ef0e771bd62d7c&)

- **Kubus Awal (Tanpa sisi depan)**

![Kubus2](https://cdn.discordapp.com/attachments/1150687865420906517/1158462996583022592/Screenshot_977.png?ex=651c563d&is=651b04bd&hm=3e2a8f536434c4f0b8e4920c0c86d772977ef937de85b314ef2fa1f05aaf1bbe&)

- **Kubus Awal (Tanpa sisi depan dan belakang)**

![Kubus4](https://cdn.discordapp.com/attachments/1150687865420906517/1158462996859859066/Screenshot_978.png?ex=651c563d&is=651b04bd&hm=da896882257a697ce9eb71c4bb334b0d42936c3bdccbc09a3ff9bfbcdd5c0a54&)

- **Kubus Awal (Hanya sisi atas dan bawah)**

![Kubus2](https://media.discordapp.net/attachments/1150687865420906517/1158462997862297721/Screenshot_980.png?ex=651c563d&is=651b04bd&hm=710143deb0a1b0721af498af7955ad084be4cd418590fa6515c9e58f81cba856&=&width=1246&height=701)

- **Kubus Awal (Hanya sisi kiri dan kanan)**

![Kubus2](https://cdn.discordapp.com/attachments/1150687865420906517/1158462997207973958/Screenshot_979.png?ex=651c563d&is=651b04bd&hm=fb2aad22cec28a5132b13971bdb69e34d2b90a5cde3b4be618f1effffbf295fd&)




# **_End Of The Line_**

```c
#include <stdio.h>

int main(){
    printf("thank you");
}
```
