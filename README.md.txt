# UTS Praktikum Algoritma dan Struktur Data 2026

## INFORMASI UJIAN
- Mata Kuliah : Praktikum Algoritma dan Struktur Data
- Semester    : Genap 2025/2026
- Media Submit: GitHub Pull Request
- Bahasa      : C++
- IDE         : Dev C++

---

# ATURAN PENGERJAAN

1. Kerjakan secara individu.
2. Dilarang menyalin pekerjaan mahasiswa lain.
3. Program wajib dapat di-compile tanpa error.
4. Gunakan struktur folder yang telah ditentukan.
5. Push dan Pull Request wajib dilakukan sebelum deadline.

---

# PEMBAGIAN SOAL

- NIM GANJIL → Soal GANJIL
- NIM GENAP → Soal GENAP

File soal tersedia pada folder:

```text
SOAL/
```

# STRUKTUR PENGUMPULAN

Mahasiswa wajib membuat folder sesuai format:

```text
Pengumpulan/
├── KELAS A/
│   └── 2503010001_WAHYU_ADIWIBOWO/
│       ├── soal1.cpp
│       └── soal2.cpp
        └── README.md
└── KELAS B/
    └── 2503010001_WAHYU_ADIWIBOWO/
        ├── soal1.cpp
        └── soal2.cpp
        └── README.md
└── KELAS C/
    └── 2503010001_WAHYU_ADIWIBOWO/
        ├── soal1.cpp
        └── soal2.cpp
        └── README.md
└── KELAS D/
    └── 2503010001_WAHYU_ADIWIBOWO/
        ├── soal1.cpp
        └── soal2.cpp
        └── README.md
└── KELAS E/
    └── 2503010001_WAHYU_ADIWIBOWO/
        ├── soal1.cpp
        └── soal2.cpp
        └── README.md
```

# STRUKTUR FILE README.md

```text
# 2503010001 - WAHYU_ADIWIBOWO
# 2503010137 - ARSY AGUNG NURMAWAN

## Informasi Pribadi
- **NIM** : 2503010001
- **Nama** : WAHYU_ADIWIBOWO
- **Kelas** : A
- *NIM* : 2503010137
- *Nama* : ARSY AGUNG NURMAWAN
- *Kelas* : A

## Informasi Ujian
- **Mata Kuliah** : Praktikum Algoritma dan Struktur Data
- **Semester** : Genap 2025/2026
- **Media Submit** : GitHub Pull Request
- **Bahasa** : C++
- **IDE** : Dev C++
- *Mata Kuliah* : Praktikum Algoritma dan Struktur Data
- *Semester* : Genap 2025/2026
- *Media Submit* : GitHub Pull Request
- *Bahasa* : C++
- *IDE* : Dev C++

---

## ANALISIS & PEMBAHASAN SOAL

### Soal 1
*Analisis:*
#include <iostream>
#include <string>
#include <iomanip> 
using namespace std;

struct Buku {
    string judul;
    string pengarang;
    int tahunTerbit;
    float harga;
};

int main() {
    int jumlah;
    Buku book[5]; 

    cout << "=== Program Data Buku ===" << endl;
    cout << "Masukkan jumlah buku (1-5): ";
    cin >> jumlah;

   
    if (jumlah < 1 || jumlah > 5) {
        cout << "Jumlah tidak valid!" << endl;
        return 0;
    }

    
    for (int i = 0; i < jumlah; i++) {
        cout << "\nData Buku ke-" << i + 1 << endl;
        cin.ignore();
		cout << "Judul: "; getline (cin, book[i].judul);
        cout << "Pengarang: "; getline(cin, book[i].pengarang);
        cout << "Tahun Terbit: "; cin>>book[i].tahunTerbit;
        cout << "harga: "; cin >> book[i].harga;
    }

    cout << endl<<string(80, '=') << endl;
    cout << left << setw(5) << "No" 
         << setw(27) << "| Judul" 
         << setw(23) << "| Pengarang" 
         << setw(11) << "| Tahun" 
         << "| Harga" << endl;
    cout <<string(80, '-')<<endl;

    float totalHarga = 0;
    int hargaTertinggi = 0;

    for (int i = 0; i < jumlah; i++) {
        cout << left << setw(5) << i + 1 
             << "| " << setw(25) << book[i].judul
             << "| " << setw(21) << book[i].pengarang
             << "| " << setw(9)  << book[i].tahunTerbit
             << "| " << fixed <<setprecision(2)<< book[i].harga << endl;
        
        totalHarga += book[i].harga;
        if (book[i].harga > book[hargaTertinggi].harga) {
            hargaTertinggi = i;
        }
    }
    cout << string(80, '-')<<endl;    
 
    cout << "1. Buku Harga Tertinggi" << endl;
    cout << "- Judul Buku    : " << book[hargaTertinggi].judul << endl;
    cout << "- Pengarang     : " << book[hargaTertinggi].pengarang << endl;
    cout << "- Tahun Terbit  : " << book[hargaTertinggi].tahunTerbit << endl;
    cout << "- Harga         : Rp" << fixed << setprecision(0) << book[hargaTertinggi].harga << endl;
    cout << "-------------------------------------------" << endl;

    float rataRata = totalHarga / jumlah;
    cout << "2. Rata-rata Harga Seluruh Buku: Rp" << fixed << setprecision(2) << rataRata << endl;


    int cariTahun;
    bool ketemu = false;
    cout << "\nMasukan Tahun terbit: ";
    cin >> cariTahun;

    cout << "\n>>> Hasil Pencarian Buku Tahun Terbit " << cariTahun << " <<<" << endl;
    for (int i = 0; i < jumlah; i++) {
        if (book[i].tahunTerbit == cariTahun) {
            cout << "Detail Buku Ditemukan:" << endl;
            cout << "- Judul Buku    : " << book[i].judul << endl;
            cout << "- Pengarang     : " << book[i].pengarang << endl;
            cout << "- Harga         : Rp" << fixed << setprecision(0) << book[i].harga << endl;
            cout << "-------------------------------------------" << endl;
            ketemu = true;
        }
    }

    if (!ketemu) {
        cout << "Pesan: Tidak ada buku yang terbit pada tahun " << cariTahun << "." << endl;
    }

    return 0;
}Collapse commentComment on lines R25 to R119coderabbitai[bot] commented on May 12, 2026 coderabbitai[bot]on May 12, 2026More actions⚠️ Potential issue | 🟡 Minor | ⚡ Quick win
Wrap both C++ solutions in fenced code blocks to avoid broken Markdown rendering.
#include lines are currently interpreted as headings, which breaks rendering and triggers MD018 lint warnings. Please wrap each solution in ```cpp fences.

Suggested fix
 ### Soal 1
 *Analisis:*
+```cpp
 `#include` <iostream>
 `#include` <string>
 `#include` <iomanip> 
 using namespace std;
 ...
 return 0;
 }
 //ARSY AGUNG NURMAWAN 2503010137
+```

 *Pembahasan:*

 ### Soal 2
 *Analisis:*
+```cpp
 `#include` <iostream>
 `#include` <string>
 using namespace std;
 ...
 return 0;
 }
 // 2503010137 ARSY AGUNG NURMAWAN
+```

 *Pembahasan:*
    
      
    

      
    

    
  

Also applies to: 128-283

🧰 Tools

🪛 markdownlint-cli2 (0.22.1)
[warning] 25-25: No space after hash on atx style heading
(MD018, no-missing-space-atx)

[warning] 26-26: No space after hash on atx style heading
(MD018, no-missing-space-atx)

[warning] 27-27: No space after hash on atx style heading
(MD018, no-missing-space-atx)



🤖 Prompt for AI Agents
Verify each finding against current code. Fix only still-valid issues, skip the
rest with a brief reason, keep changes minimal, and validate.

In `@README.md` around lines 25 - 119, The README contains raw C++ source starting
with `#include` lines (e.g., the blocks beginning with "#include <iostream>" and
the second solution block) which Markdown treats as headings and causes MD018
lint warnings; wrap each full C++ solution block in fenced code blocks using
```cpp ... ``` so the `#include` lines are treated as code (apply this to both
solution blocks around the content that includes symbols like struct Buku,
main(), and the second solution starting with `#include` <iostream> and using
namespace std;). Ensure the opening ```cpp appears immediately before the first
`#include` and the closing ``` after the final comment (e.g., "//ARSY AGUNG
NURMAWAN ..." and the second solution's final comment) so the entire snippet
renders correctly.

    
      
    

      
    

    
  



ReactWrite a replyResolve comment
//ARSY AGUNG NURMAWAN 2503010137


*Pembahasan:*

...(uraikan analisis dan pembahasan soal 1)...

### Soal 2
*Analisis:*
#include <iostream>
#include <string>
using namespace std;

#define max 5

struct riwayatTransaksi {
	int top;
	string data[max];
};

void init (riwayatTransaksi &s){
	s.top = -1;
}

bool isFull (riwayatTransaksi s){
	return s.top == max -1;
}
bool isEmpty (riwayatTransaksi s){
	return s.top == -1;
}

void push (riwayatTransaksi &s, string transaksi){
	if (isFull(s)){
		cout<<"Stack Penuh!"<<endl;
	}else {
		s.top++;
		s.data[s.top]= transaksi;
		cout<<"Menambahkan Data Transaksi: "<<transaksi<<endl;
	}
}

void pop(riwayatTransaksi &s){
	if(isEmpty(s)){
		cout<<"Data Kosong!"<<endl;
	}else {
		cout<<"Menghapus data Teratas dilakukan: "<<s.data[s.top]<<endl;
		s.top--;
	}
}

void peek (riwayatTransaksi s){
	if(!isEmpty(s)){
		cout<<"Data Teratas: "<<s.data[s.top]<<endl;
	}else {
		cout<<"Data Kosong!";
	}
}

void display (riwayatTransaksi s){
	if(isEmpty(s)){
		cout<<"Data Kosong!"<<endl;
	}else {
		cout<<"Data Transaksi: "<<endl;
	for (int i = s.top; i >= 0; i--){
   		 cout << "[" << s.data[i] <<"]"<< endl;
		}
	}
}

...(uraikan analisis dan pembahasan soal 2)...
//Bagian Queue
string data[max];
int front = -1;
int rear = -1;

bool isFull (){
	return rear == max -1;
}
bool isEmpty (){
	return front == -1;
}

void enqueue (string antrian){
	if(isFull()){
		cout<<"Antrian Penuh!"<<endl;
	}else{
		if(isEmpty()){
			front = 0;
		}
		rear++;
		data[rear]= antrian;
		cout<<"Masuk Antrian: "<<antrian<<endl;
	}
}

void dequeue (){
	if(isEmpty()){
		cout<<"Antrian Kosong!"<<endl;
	}else {
		cout<<"\nAntrian Depan Keluar: "<<data[front]<<endl;
		if(front == rear){
			front = rear = -1;
		}else{
			front++;
		}
	}
}

void peek (){
	if(!isEmpty()){
		cout<<"Antrian Terdepan: "<<data[front]<<endl;
	}else {
		cout<<"Antrian Tosong!"<<endl;
	}
}

void display (){
	if(isEmpty()){
		cout<<"Antrian Kosong!"<<endl;
	}else{
		cout<<"Daftar Antrian: ";
		for(int i =front; i<= rear; i++){
			cout<<"["<<data[i]<<"]";
		}
		cout<<endl;
	}
}

int main (){
	riwayatTransaksi tumpukan;
	init (tumpukan);
	cout<<"=====STACK====="<<endl;
	push(tumpukan, "T001");
	push(tumpukan, "T002");	
	push(tumpukan, "T003");
	push(tumpukan, "T004");
	
	cout<<endl;
	peek(tumpukan);
	
	cout<<endl;
	pop(tumpukan);
	pop(tumpukan);
	
	cout<<endl;
	display(tumpukan);
	
	
	cout<<"\n=====QUEUE====="<<endl<<endl;
	enqueue("Budi");
	enqueue("Sari");
	enqueue("Eko");
	
	cout<<endl;
	peek();
	
	dequeue();
	display();
	
	cout<<endl;
	enqueue("Dewi");
	
	display();

	return 0;
}
// 2503010137 ARSY AGUNG NURMAWAN


*Pembahasan:*
-

---

## SUMBER BELAJARs

Sebutkan sumber belajar yang digunakan, contohnya:

- Modul Praktikum Algoritma dan Struktur Data
- Modul Pointer
- Modul Rekursif
- Modul Struktur Data Dasar
- Buku Algoritma dan Pemrograman Modern
- Video pembelajaran online (YouTube, Coursera, dll.)
- Stack Overflow
- Dokumentasi resmi bahasa C++
```
- isi