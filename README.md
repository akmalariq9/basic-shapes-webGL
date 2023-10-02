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

Fungsi draw dalam kode untuk _RGB Triangle_ memiliki tugas utama untuk menggambar dua segitiga pada elemen _canvas_ webGL.

```c++
      function draw() {
        gl.clearColor(0, 0, 0, 1); // specify the color to be used for clearing
        gl.clear(gl.COLOR_BUFFER_BIT); // clear the canvas (to black)

        /* Set up values for the "coords" attribute */

        let coords = new Float32Array([-0.5, -0.5, -0.5, 0.5, 0.5, 0.5]);

        gl.bindBuffer(gl.ARRAY_BUFFER, bufferCoords);
        gl.bufferData(gl.ARRAY_BUFFER, coords, gl.STREAM_DRAW);
        gl.vertexAttribPointer(attributeCoords, 2, gl.FLOAT, false, 0, 0);
        gl.enableVertexAttribArray(attributeCoords);

        /* Set up values for the "color" attribute */

        let color = new Float32Array([0, 1, 0, 1, 0, 0, 0, 0, 1]);

        gl.bindBuffer(gl.ARRAY_BUFFER, bufferColor);
        gl.bufferData(gl.ARRAY_BUFFER, color, gl.STREAM_DRAW);
        gl.vertexAttribPointer(attributeColor, 3, gl.FLOAT, false, 0, 0);
        gl.enableVertexAttribArray(attributeColor);

        /* Draw the triangle. */

        gl.drawArrays(gl.TRIANGLES, 0, 3);

        let secondcoord = new Float32Array([-0.5, -0.5, 0.5, 0.5, 0.5, -0.5]);

        gl.bindBuffer(gl.ARRAY_BUFFER, bufferCoords);
        gl.bufferData(gl.ARRAY_BUFFER, secondcoord, gl.STREAM_DRAW);
        gl.vertexAttribPointer(attributeCoords, 2, gl.FLOAT, false, 0, 0);
        gl.enableVertexAttribArray(attributeCoords);

        /* Set up values for the "secondcolor" attribute */
        let secondcolor = new Float32Array([0, 1, 0, 0, 0, 1, 1, 0, 0]);

        gl.bindBuffer(gl.ARRAY_BUFFER, bufferColor);
        gl.bufferData(gl.ARRAY_BUFFER, secondcolor, gl.STREAM_DRAW);
        gl.vertexAttribPointer(attributeColor, 3, gl.FLOAT, false, 0, 0);
        gl.enableVertexAttribArray(attributeColor);

        /* Draw the second triangle. */
        gl.drawArrays(gl.TRIANGLES, 0, 3);
      }
```

Pertama, fungsi ini mengatur _background_ elemen _canvas_ menjadi hitam dengan menggunakan `gl.clearColor(0, 0, 0, 1)`. Kemudian _canvas_ tersebut dikosongkan menggunakan _function_ `gl.clear(gl.COLOR_BUFFER_BIT)`.

Setelah persiapan awal, fungsi ini mulai membuat atribut koordinat dan warna untuk segitiga pertama. Koordinat segitiga pertama ditentukan pada bagian `let coords = new Float32Array([-0.5, -0.5, -0.5, 0.5, 0.5, 0.5])`, dan data warna untuk setiap koordinat segitiga pertama diatur dalam `let color = new Float32Array([0, 1, 0, 1, 0, 0, 0, 0, 1])`. Selanjutnya, _buffer_ untuk koordinat dan warna digabungkan, bersamaan dengan atribut lain yang juga diaktifkan.

Setelah data segitiga selesai dibuat, maka segitiga akan digambar kedalam _canvas_ dengan `gl.drawArrays(gl.TRIANGLES, 0, 3)`.

Selanjutnya, fungsi `draw` melakukan hal yang serupa untuk segitiga kedua dengan variabel `secondcoord` dan `secondcolor`. Fungsi `secondcoord` mendefinisikan koordinat dari segitiga kedua, sedangkan `secondcolor` mendefinisikan data warna untuk setiap titik pada segitiga kedua. Setelah data segitiga kedua disiapkan, segitiga kedua juga digambar dalam canvas menggunakan `gl.drawArrays(gl.TRIANGLES, 0, 3)`.

Fungsi `draw` yang telah dijalankan akan menampilkan dua segitiga pada elemen _canvas_ WebGL, di mana masing-masing segitiga memiliki koordinat dan warna yang berbeda. Kedua segitiga tersebut akan membentuk sebuah persegi sesuai warna yang diberikan sebelumnya.

## **_Screenshot Ouput_**

Berikut adalah _Screenshot output_ dari code tersebut:

![Doubletriangle](https://media.discordapp.net/attachments/1150687865420906517/1158475870365831329/Screenshot_982.png?ex=651c623a&is=651b10ba&hm=678fc055d3bfcac7b8286e57c741ee30f5f748bc664217da1be3c18d2f2717d3&=&width=1246&height=701)

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
