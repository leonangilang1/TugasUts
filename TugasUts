#include <iostream>
#include <string>

using namespace std;

struct Jurusan {
    string kode;
    string nama;
    int pembayaranAwal;
    int jumlahCicilan;
    int besarCicilan;
};


void tampilkanDataJurusan(Jurusan jurusan[], int jumlahJurusan) {	
    cout << "Kode | Jurusan                | Pembayaran Awal | Jumlah Cicilan | Besar Cicilan\n";
    cout << "--------------------------------------------------------------\n";
    for (int i = 0; i < jumlahJurusan; i++) {
        cout << jurusan[i].kode << "   | " 
             << jurusan[i].nama << "  | " 
             << jurusan[i].pembayaranAwal << "           | " 
             << jurusan[i].jumlahCicilan << "          | " 
             << jurusan[i].besarCicilan << "\n";
    }
}

int main() {
    Jurusan jurusan[] = {
        {"SI", "Sistem Informasi", 2100000, 7, 300000},
        {"TI", "Teknik Informatika", 2500000, 7, 300000},
        {"KA", "Komputer Akutansi", 1750000, 6, 200000},
        {"MI", "Manajemen Informatika", 1500000, 6, 2500000}
    };

    const int jumlahJurusan = sizeof(jurusan) / sizeof(jurusan[0]);
    char lagi;
	
	cout << "+----------------------------------------------------------------+\n";
	cout << "|      Aplikasi Pembayaran Uang Kuliah Universitas Tribuana      |\n";
	cout << "+----------------------------------------------------------------+\n";
	
    do {
        string namaMahasiswa, npm, kodeJurusan;
        int pembayaranAwal, jumlahCicilan, besarCicilan;
        
        cout << "Nama Mahasiswa: ";
        getline(cin, namaMahasiswa);
        cout << "NPM: ";
        getline(cin, npm);
        cout << endl;

        tampilkanDataJurusan(jurusan, jumlahJurusan);
        
        cout << endl;

        cout << "Kode Jurusan: ";
        cin >> kodeJurusan;

        bool ditemukan = false;
        string namaJurusan;
        for (int i = 0; i < jumlahJurusan; i++) {
            if (jurusan[i].kode == kodeJurusan) {
                pembayaranAwal = jurusan[i].pembayaranAwal;
                jumlahCicilan = jurusan[i].jumlahCicilan;
                besarCicilan = jurusan[i].besarCicilan;
                namaJurusan = jurusan[i].nama;  // Simpan nama jurusan
                ditemukan = true;
                break;
            }
        }

        if (!ditemukan) {
            cout << "Kode Jurusan tidak ditemukan!\n";
            continue;
        }

        // Tampilkan nama jurusan
        cout << "Jurusan: " << namaJurusan << endl;

        // Hitung total uang kuliah
        int uangKuliah = pembayaranAwal + (jumlahCicilan * besarCicilan);
        cout << "Uang Kuliah: " << uangKuliah << endl;

        // Hitung pembayaran terbayar
        cout << "Masukkan Pembayaran Ke-i (1 s/d " << jumlahCicilan << "): ";
        int pembayaranKe;
        cin >> pembayaranKe;

        if (pembayaranKe < 1 || pembayaranKe > jumlahCicilan) {
            cout << "Pembayaran Ke-i tidak valid!\n";
            continue;
        }

        int uangKuliahTerbayar = pembayaranAwal + ((pembayaranKe - 1) * besarCicilan);
        cout << "Uang Kuliah Terbayar setelah " << pembayaranKe << " kali cicilan: " << uangKuliahTerbayar << endl;

        // Hitung sisa uang kuliah
        int sisaUangKuliah = uangKuliah - uangKuliahTerbayar;
        cout << "Sisa Uang Kuliah: " << sisaUangKuliah << endl;

        cout << "Masih ingin menghitung? (Y/T): ";
        cin >> lagi;
        cin.ignore(); // Mengabaikan karakter newline setelah cin
        
        cout << "+----------------------------------------------------------------+\n";
        
        cout << endl;

    } while (lagi == 'Y' || lagi == 'y');

    return 0;
}
