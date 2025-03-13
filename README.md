<div align="center">

# **Reflection - Pemrograman Lanjut**  
## Daniel Ferdiansyah, 2306275052  

</div>

---

## Test Screenshot



`all-student` endpoint

![Screenshot 2025-03-13 144001](https://github.com/user-attachments/assets/52cfd447-973f-42c5-a1d8-fdb15cdf3048)

![Screenshot 2025-03-13 144637](https://github.com/user-attachments/assets/f53515c5-1b01-4ba7-8fd8-409312a51f6e)

![Screenshot 2025-03-13 144749](https://github.com/user-attachments/assets/717f6aef-6d1b-4a33-aa3e-bb9bc6e74f13)

`all-student-name` endpoint

![Screenshot 2025-03-13 144233](https://github.com/user-attachments/assets/5170f126-3ea7-4384-8103-b9ba539859d6)

![Screenshot 2025-03-13 144650](https://github.com/user-attachments/assets/baa9f154-b221-4b9e-a77f-2aaf6aee732e)

![Screenshot 2025-03-13 144816](https://github.com/user-attachments/assets/ceb155ee-00c4-4e9f-895b-937c02b9b247)

`highest-gpa` endpoint

![Screenshot 2025-03-13 144356](https://github.com/user-attachments/assets/a0be77ad-5c75-4d08-8365-e3f5fad7498e)

![Screenshot 2025-03-13 144705](https://github.com/user-attachments/assets/40fd6c72-5d84-40c1-a3ee-d2e8ce71ccf5)

![Screenshot 2025-03-13 144827](https://github.com/user-attachments/assets/237e8e19-593b-4233-a535-32e658f30475)

---

## After Optimization

`all-student` endpoint

![Screenshot 2025-03-13 150552](https://github.com/user-attachments/assets/76befd8c-317f-4de5-abfc-31d84584a590)

![Screenshot 2025-03-13 150726](https://github.com/user-attachments/assets/fd884541-7e27-47c0-92d5-168b3b3098ad)

![Screenshot 2025-03-13 150750](https://github.com/user-attachments/assets/722ca179-82f6-4afb-8ec9-580a4e6ddb68)

`all-student-name` endpoint

![image](https://github.com/user-attachments/assets/fa1dbf9d-d171-4f92-acfc-4175a203f310)

![image](https://github.com/user-attachments/assets/f31e9869-1f84-4f78-8866-e264e28abe49)

![image](https://github.com/user-attachments/assets/076b4da9-1fea-4bf7-a79b-bbb367ecd377)

`highest-gpa` endpoint

![image](https://github.com/user-attachments/assets/0ed498f3-2d68-43a8-89b4-7707535bd149)

![image](https://github.com/user-attachments/assets/c9413177-83f1-4898-8bc0-dcf19a2b0da2)

![image](https://github.com/user-attachments/assets/af541124-e2dd-4231-8658-fa9dd2846f96)

**Conclusion**

Dapat dilihat setelah adanya optimisasi dengan refacoring beberapa method, performa untuk ketiga endpoint meningkat drastis.

- Endpoint `all-student` menjadi lebih cepat **4200% sampai 4800%**. Refactoring secara signifikan dilakukan pada method `getAllStudentsWithCourses()`
  
- Endpoint `all-student-name` menjadi lebih cepat **15% sampai 20%**. Tidak banyak hal yang bisa dioptimize, tapi tetap ada optimasi cukup pada method `joinStudentNames()`

- Endpoint `highest-gpa` menjadi lebih cepat **hingga 262.5%**. 
 
## Reflection

1. Perbedaan utama antara pengujian performa dengan *JMeter* dan *profiling* dengan *IntelliJ Profiler* adalah pendekatannya. *JMeter* digunakan untuk melakukan uji load dan stres dengan mensimulasikan banyak pengguna sekaligus untuk mengukur kinerja aplikasi dalam skenario dunia nyata. Sedangkan *IntelliJ Profiler* digunakan untuk menganalisis penggunaan CPU, memori, dan thread di dalam aplikasi untuk menemukan bagian kode yang tidak efisien atau menjadi *bottleneck*.  

2. Proses *profiling* membantu mengidentifikasi titik lemah dalam aplikasi dengan memberikan informasi tentang penggunaan sumber daya seperti CPU, memory, dan IO. Dengan melihat metode mana yang memakan waktu paling lama atau alokasi memory yang tinggi, kita dapat menemukan bagian kode yang perlu dioptimalkan.  

3. *IntelliJ Profiler* cukup efektif dalam membantu menganalisis dan mengidentifikasi *bottleneck* dalam modul kali ini. Dengan fitur seperti *CPU profiling*, *memory allocation tracking*, dan *thread analysis*, saya dapat menemukan operasi yang paling membebani sistem dan memperbaikinya secara langsung, misalnya pada metode `getAllStudentsWithCourses()` yang memakan waktu dan memori cukup banyak.

4. Tantangan utama dalam pengujian performa dan *profiling* adalah menginterpretasikan hasil dengan benar serta memastikan bahwa hasil yang didapat benar-benar mencerminkan kondisi aplikasi dalam *environment* produksi. Salah satu cara mengatasinya adalah dengan melakukan pengujian dalam berbagai skenario yang realistis dan mengkombinasikan hasil dari beberapa tools analisis.  

5. Manfaat utama menggunakan *IntelliJ Profiler* adalah kemudahan dalam melihat penggunaan sumber daya aplikasi secara detail, mendeteksi method yang memakan waktu lama, mengidentifikasi *memory leaks*, dan membantu dalam memahami bagaimana aplikasi bekerja di tingkat sistem.  

6. Jika hasil *profiling* dengan *IntelliJ Profiler* tidak sepenuhnya konsisten dengan temuan dari pengujian performa menggunakan *JMeter*, langkah yang bisa dilakukan adalah membandingkan lingkungan pengujian, jumlah data yang digunakan, serta mengulang pengujian dengan parameter yang lebih seragam untuk mencari penyebab perbedaan hasil tersebut.  

7. Strategi utama dalam mengoptimalkan kode setelah menganalisis hasil pengujian dan *profiling* adalah dengan melakukan *refactoring* pada metode yang tidak efisien, mengurangi alokasi *memori* yang tidak perlu, serta meningkatkan algoritma yang digunakan. Untuk memastikan perubahan tidak merusak fungsionalitas aplikasi, dilakukan pengujian *regresi* dan validasi hasil dengan *benchmark* sebelum dan sesudah optimasi.
