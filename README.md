Assalamu'alaikum Warohmatullahi Wabarokatuh
Saya pribadi memohon ampun kepada Allah Subhanahu Wata'ala, ampunilah keluargaku, ayah ibuku, saudaraku, keturunanku
serta seluruh muslimin dan muslimat di seluruh dunia ini sampai hari kiamat Aamiin

Silahkan pelajari dan kembangkan fungsi validasi request restful API format JSON

ada masalah menurut saya ketika saya buat API menggunakan springboot
diminta validasi request json yang masuk sebelum di proses selanjutnya
-validasi jika salah satu field tidak dikirim
-validasi jika field mandatory diinput kosong atau kepanjangan

awalnya saya buat manual satu persatu, contoh:
if(field1.getValue() > 11){
   System.out.println("Error");
}
rasanya coding seperti itu ga baik, semuanya manual.. bayangkan jika field ada banyak
berapa jam develop

saya mencoba buat fungsi yg dinamis dipakai, dibuatlah fungsi ini 

semoga bermanfaat
