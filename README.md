# **Business Intelligence Analyst Project Based Internship Program**

## Soal 1
Tentukan masing-masing primary key pada 4 dataset penjualan

Primary key tabel Customer : **CustomerID**

Primary key tabel Products : **ProdNumber**

Primary key tabel Orders : **OrderID**

Primary key tabel ProductCategory : **CategoryID**

## Soal 2
Tentukan relationship dari ke-4 tabel tersebut

**1. Hubungan many-to-one antara tabel "Orders" dengan tabel "Products"**

Karena banyaknya "Orders" dapat menggunakan "Products" yang sama, tetapi "Products" hanya dapat menggunakan satu "Orders".

**2. Hubungan one-to-many antara tabel "Customers" dengan tabel "Orders"**

Karena satu “Customers” dapat melakukan banyak “Orders”, tetapi setiap “Orders” hanya dapat dilakukan oleh satu “Customers”.

**3. Hubungan many-to-one antara tabel "Products" dengan tabel "ProductCategory"**

Karena banyaknya “Products" termasuk ke dalam satu "ProductCategory" tertentu.

## Soal 3
Sebagai BI Analyst PT Sejahtera Bersama, kita akan membuat sebuah table master yang berisikan informasi :

CustomerEmail (cust_email)
CustomerCity (cust_city)
OrderDate (order_date)
OrderQty (order_qty)
ProductName (product_name)
ProductPrice (product_price)
ProductCategoryName (category_name)
TotalSales (total_sales)
Urutkan data tersebut berdasarkan tanggal transaksi yang paling awal sampai yang paling akhir.

````sql
SELECT
o.Date AS order_date,
pc.CategoryName AS category_name,
p.ProdName AS product_name,
p.Price AS product_price,
o.Quantity AS order_qty,
(p.Price * o.Quantity) AS total_sales,
c.CustomerEmail AS cust_email,
c.CustomerCity AS cust_city
FROM
task_5.Orders o
JOIN task_5.Customers c ON o.CustomerID = c.CustomerID
JOIN task_5.Products p ON o.ProdNumber = p.ProdNumber
JOIN task_5.ProductCategory pc ON p.Category = pc.CategoryID
ORDER BY order_date ASC;
````

## Soal 4
Dari hasil tabel yang dibuat pada soal nomor 3, simpanlah hasilnya dalam bentuk CSV. Dengan menggunakan Looker Studio, buatlah visualisasi yang menampilkan data penjualan tersebut. Visualisasi tersebut harus berisi minimal :

Total keseluruhan sales
Total keseluruhan sales berdasarkan kategori produk
Total keseluruhan qty berdasarkan kategori produk
Total sales berdasarkan kota
Total qty berdasarkan kota
Top 5 kategori produk yang paling tinggi salesnya
Top 5 kategori produk yang paling tinggi qtynya

![image](https://github.com/Kyielas/Rakamin-X-Bank-Muamalat-Digital-User-Churn-Dashboard/blob/main/Rakamin%20X%20Bank%20Muamalat%20Digital%20User%20Churn%20Dashboard.png)

[Looker Studio [Click Here]](https://lookerstudio.google.com/reporting/6050d1ec-caff-4208-9ac6-15feb2649278)

## Soal 5
Sebagai BI analyst PT Sejahtera Bersama, apa yang bisa anda usulkan untuk mempertahankan penjualan ataupun menaikkan penjualan dengan tabel transaksi detail yang sudah ada?

**1. Sesuaikan penawaran produk berdasarkan preferensi wilayah**

Berdasarkan proporsi penjualan produk di kota-kota teratas, disarankan untuk menyesuaikan penawaran produk dengan preferensi wilayah. Misalnya, di kota Washington, produk "Robots" sangat populer, jadi bisa memperkuat stok produk dalam kategori ini di wilayah tersebut. Selain itu lakukan juga survei pelanggan atau wawancara dengan mereka untuk mendapatkan wawasan langsung tentang preferensi dan kebutuhan mereka.

**2. Memperluas wilayah dan pemasaran di lima kota teratas**

Lima kota dengan total penjualan tertinggi adalah Washington, Houston, Sacramento, San Diego, dan Albany. Buka franchise dan tingkatkan kampanye pemasaran khusus di setiap kota dengan total penjualan tertinggi.

**3. Mengoptimalkan kategori produk**

Kategori "Robots" adalah kontributor utama untuk total penjualan, namun "eBooks" adalah yang terlaris dalam hal jumlah barang terjual. Kembangkan produk dalam kategori "Robots" atau meningkatkan promosi untuk "eBooks."

