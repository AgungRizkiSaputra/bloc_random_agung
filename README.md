Lanjutan dari GitHub sebelumnya : https://github.com/AgungRizkiSaputra/StreamBuilderAgung

# Praktikum 7 : BloC Pattern

### P7: Jawaban Soal 13

Maksud dari praktikum ini adalah menjelaskan bagaimana cara mengimplementasikan BloC atau "Business Logic Component" yang memiliki lapisan antara semua sumber data dan UI. Alasan utama menggunakan BLoC adalah memisahkan logika bisnis aplikasi dengan presentasi UI.

#### Letak Konsepnya

1. Class RandomNumberBloc
   Class ini bertanggung jawab untuk menangani logika bisnis, yaitu menghasilkan angka acak dan mengalirkannya ke UI melalui Stream.

   - generateRandom: merupakan event input dalam bentuk Sink<void>. Event ini akan memicu BLoC untuk menghasilkan angka acak.
   - randomNumber: merupakan state output dalam bentuk Stream<int> yang akan didengarkan oleh UI.

2. Widget StreamHomepage

   - StreamBuilder mendengarkan randomNumber dari BLoC.
   - Saat data di Stream berubah, builder akan dipanggil ulang untuk memperbarui UI dengan data terbaru.

3. Trigger melalui FloatingActionButton
   - Saat tombol ditekan, event null dikirim ke generateRandom, yang men-trigger logika untuk menghasilkan angka acak.

<img src="https://github.com/AgungRizkiSaputra/bloc_random_agung/blob/main/image/GIFP7soal13.gif" width="150px">
