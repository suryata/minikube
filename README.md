### 1. Compare the application logs before and after you exposed it as a Service.
Try to open the app several times while the proxy into the Service is running.
What do you see in the logs? Does the number of logs increase each time you open the app?
Terdapat perbedaan antara log aplikasi sebelum dan setelah Service di-expose. Setelah Service di-expose, aplikasi dapat menerima request dari luar, sehingga pada log akan tercatat request-request yang diterima. Misalnya, seperti yang terlihat pada log, ada beberapa entri untuk permintaan GET, yang merupakan hasil dari melakukan refresh atau akses berulang kali ke Service hello-node. Ini menunjukkan bahwa aplikasi secara aktif menangani permintaan masuk setelah dijadikan sebagai Service.
![alt text](image.png)


### 2. Notice that there are two versions of `kubectl get` invocation during this tutorial section.
The first does not have any option, while the latter has `-n` option with value set to `kube-system`.
What is the purpose of the `-n` option and why did the output not list the pods/services that you
explicitly created?
Opsi -n digunakan untuk menentukan namespace tertentu dalam kluster Kubernetes. Namespace adalah cara untuk membagi sumber daya kluster ke dalam kelompok-kelompok yang terisolasi. Jadi, ketika perintah kubectl get dijalankan dengan -n kube-system, perintah tersebut hanya akan menampilkan sumber daya yang berada di dalam namespace kube-system. Alasan output tidak menampilkan pod atau service secara eksplisit adalah karena sumber daya tersebut kemungkinan besar dibuat di namespace default atau namespace lain yang tidak termasuk kube-system.

