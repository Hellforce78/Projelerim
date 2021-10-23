# Projelerim
#include <stdio.h>
#include <stdlib.h>
#include <math.h>
int main()
{
	int  islem,bakiye=7800,tutar,i,a,fatura_sec;
	int su,elektrik,internet,dogalgaz;
	int k_ad;
	int parola;
	int ad,paswword;
	printf("ID Giriniz \n");
	scanf("%d",&ad);
	printf("Sifrenizi Giriniz \n");
	scanf("%df",&paswword);
	FILE*tc = fopen("tc.txt","r+");
	fscanf(tc,"%d",&k_ad);
	FILE*sifre = fopen("sifre.txt", "r+");
	fscanf(sifre,"%d",&parola);

	if (ad == k_ad && parola == paswword)
{
	for (i = 0; i < 2; i++)
	{	
	printf("Yapacaginiz Islemi Seciniz \n");
	printf("[1] Bakiye Goruntule \n[2] Para Cek \n[3] Para Yatir \n[4] Fatura Islemleri \n[5] Kart Iade ");
	scanf("%d",&islem);
			switch (islem)
			{
			case 1:
				printf("<----------------------------------->\n");
				printf("Bakiyeniz = %d \n",bakiye);
				printf("<----------------------------------->\n");
				i=0;
				break;
			case 2:
				printf("Tutar Giriniz =");
				scanf("%d",&tutar);
			if (bakiye >= tutar)
			{
				bakiye = bakiye - tutar;
				printf("<----------------------------------->\n");
				printf("Paraniz Hazirlandi Lutfen Aliniz Yeni Bakiyeniz = %d\n",bakiye);
				printf("<----------------------------------->\n");
			}
			else
			{
				printf("<----------------------------------->\n");
				printf("Yeterli Bakiyeniz Bulunmamaktadir \n");
				printf("<----------------------------------->\n");
			}
				i=0;
				break;
			case 3:
				printf("Tutar Giriniz =");
				scanf("%d",&tutar);
				bakiye = bakiye + tutar;
				printf("<----------------------------------->\n");
				printf(" Yeni Bakiyeniz = %d\n",bakiye);
				printf("<----------------------------------->\n");
				i=0;
				break;
			case 4:
				printf("<----------------------------------->\n");
				printf("Odemek Istediginiz Faturayi Seciniz\n");
				printf("<----------------------------------->\n");
				for (size_t a = 0; a < 2 ;a++)
				{
					printf("[1]Su Faturasi \n[2] Elektirik Faturasi \n[3] Internet Faturasi \n[4] Dogalgaz Faturasi \n[5] Geri");
					scanf("%d",&fatura_sec);
					switch (fatura_sec)
					{
					case 1:
						printf("Odemek Istediginiz Miktari Giriniz =");
						scanf("%d",&su);
						bakiye= bakiye - su ;
						printf("<----------------------------------->\n");
						printf("Su Faturaniz Odendi\n");
						printf("Kalan Bakiye = %d\n",bakiye);
						printf("<----------------------------------->\n");
						a=0;
						break;
					case 2:
						printf("Odemek Istediginiz Miktari Giriniz =");
						scanf("%d",&elektrik);
						bakiye= bakiye - elektrik ;
						printf("<----------------------------------->\n");
						printf("Elektirik Faturaniz Odendi\n");
						printf("Kalan Bakiye = %d\n",bakiye);
						printf("<----------------------------------->\n");
						a=0;
						break;
					case 3:
						printf("Odemek Istediginiz Miktari Giriniz =");
						scanf("%d",&internet);
						bakiye= bakiye - internet ;
						printf("<----------------------------------->\n");
						printf("Internet Faturaniz Odendi\n");
						printf("Kalan Bakiye = %d\n",bakiye);
						printf("<----------------------------------->\n");
						a=0;
						break;
					case 4:
						printf("Odemek Istediginiz Miktari Giriniz =");
						scanf("%d",&dogalgaz);
						bakiye= bakiye - su ;
						bakiye= bakiye - dogalgaz ;
						printf("<----------------------------------->\n");
						printf("Dogalgaz Faturaniz Odendi\n");
						printf("Kalan Bakiye = %d\n",bakiye);
						printf("<----------------------------------->\n");
						a=0;
						break;
					case 5:
						break;
					
					default:
						printf("Eksik Veya Hatali Tuslamaya Yaptiniz");
						break;
					}

				}
			
			case 5:
			break;
			printf("Cikmak icin Bir Tusa Basiniz");
			default:
				printf("Eksik Veya Hatali Tuslama Yaptiniz\n");
				i=0;
				break;
			}
			getch();
	}
}
else
{
	printf("Yanlis Tuslama Yaptiniz \n");
}
fclose(sifre);
fclose(tc);
	system("pause");
	return (0);
}
