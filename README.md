```cpp
#include <iostream>
#include <string>
using namespace std;

bool giriskt() {

    string username, password, trueus, truepas;
    short int hak = 3;

    trueus = "root";
    truepas = "admin";

    while (true) {

        cout << "Enter a username" << endl;
        cin >> username;

        cout << "Enter a password" << endl;
        cin >> password;

        if (username != trueus || password != truepas) {

            hak--;

            cout << "Hatali giris denemesi" << endl;
            cout << "Kalan hak: " << hak << endl;

            if (hak == 0) {
                cout << "Hak denemesi sona erdi, program kapatiliyor." << endl;
                return false;
            }
        }
        else {

            cout << "Giris basarili..." << endl;
            return true;
        }
    }
}


bool secim() {
    int sayisalislem, sayi1, sayi2;
    short int secims, secim;
    string personelad, personelsoy, persosicil;
    while (true) {

        cout << "\n--- SYSTEM MENU ---" << endl;
        cout << "Personel girisi icin | 1 | " << endl;
        cout << "Sistem durumu kontrol icin | 2 | " << endl;
        cout << "Sayisal islem icin | 3 | " << endl;
        cout << "Cikis icin | 4 | " << endl;

        cout << "Seciminiz: ";
        cin >> secims;

        switch (secims) {

        case 1:
            cout << "Personel giris paneline aktarildiniz." << endl;
            cout << "Lutfen personel adi giriniz." << endl;
            cin >> personelad;
			cout << "Lutfen personel soyadi giriniz." << endl;
            cin >> personelsoy; 
			cout << "Lutfen personel sicil numarasini giriniz." << endl;
            cin >> persosicil;      
			cout << "---------------------------" << endl;
			cout << "Personel adi: " << personelad << endl;
			cout << "Personel soyadi: " << personelsoy << endl;
			cout << "Personel sicil numarasi: " << persosicil << endl;
            cout << "---------------------------" << endl;
            return true;

        case 2:
            cout << "Sistem durumu kontrol ediliyor." << endl;
            cout << "Sistem durumu aktif..." << endl;
            return true;

        case 3:
            cout << "Sayisal islem menusu, toplama icin 1, cikarma icin 2, carpma icin 3, bolme icin 4 seciniz." << endl;
            cin >> secim;
            switch (secim) {
            case 1: cout << "Toplama islemine giris sagladiniz. , toplamak istediginiz ilk sayiyi giriniz. "<< endl;
                cin >> sayi1;
				cout << "İkinci sayiyi giriniz." << endl;
                cin >> sayi2;
                sayisalislem = sayi1 + sayi2;
                cout << "Toplama sonucu: " << sayisalislem << endl; break;
			case 2: cout << "Cikarma islemine giris sagladiniz. , cikarmak istediginiz ilk sayiyi giriniz. " << endl; 
				cin >> sayi1;
				cout << "İkinci sayiyi giriniz." << endl;
                cin >> sayi2;
				sayisalislem = sayi1 - sayi2;
                cout << "Cikarma sonucu: " << sayisalislem << endl; break;
			case 3: cout << "Carpma islemine giris sagladiniz. , carpacak istediginiz ilk sayiyi giriniz. " << endl;
                cin >> sayi1;
				cout << "İkinci sayiyi giriniz." << endl;
                cin >> sayi2;
				sayisalislem = sayi1 * sayi2;
				cout << "Carpma sonucu: " << sayisalislem << endl; break;
			case 4: cout << "Bolme islemine giris sagladiniz. , bolmek istediginiz ilk sayiyi giriniz. " << endl;
				cin >> sayi1;
				cout << "İkinci sayiyi giriniz." << endl;
                cin >> sayi2;
				if (sayi2 == 0) {
					cout << "Hata: Sifira bolme hatasi." << endl;
				}
				else {
					sayisalislem = sayi1 / sayi2;
					cout << "Bolme sonucu: " << sayisalislem << endl;
				}
			default: cout << "Gecersiz secim, tekrar deneyiniz." << endl;
				break;
            }

            return true;

        case 4:
            cout << "Cikis yapiliyor." << endl;
            return false;

        default:
            cout << "Gecersiz secim, tekrar deneyiniz." << endl;
            break;
        }
    }
}
void selamla() {
    cout << "Hos geldiniz bu benim fonksiyonlara yeni ogrenip kullandigim ilk projelerimden birisi şuan kendimi deniyorum sadece." << endl;
    cout << "Buraya kadar geldiysen tesekkur ederim." << endl;
}


int main() {

    cout << "Welcome To Minilogin system.." << endl;

    if (giriskt()) {

        cout << "Sisteme erisim aciliyor." << endl;

        while (secim()) {

            cout << "Menu devam ediyor..." << endl;

        }
        selamla();
    }
    else {

        cout << "Giris basarisiz." << endl;
        cout << "Program kapatiliyor..." << endl;

    }

    return 0;
}

