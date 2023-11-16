<h1>UTS Pemograman Mobile</h1>

<table align="center">
  <tr>
    <th colspan="2">DATA MAHASISWA</th>
  </tr>
  <tr>
    <td>Nama</td>
    <td>Alif Nur Fathlii Amarta</td>
  </tr>
  <tr>
    <td>NIM</td>
    <td>312210326</td>
  </tr>
  <tr>
    <td>Kelas</td>
    <td>TI.22.A3</td>
  </tr>
</table>

### Dokumentasi

Deklarasi variable

    private int mCount;
    private  int n1 = 1;
    private int n2 = 0;
    private TextView mShowCount;
    private EditText mEditText;

Inisialisasi variable dalam ```onCreate()```

    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_toast);
        mShowCount = (TextView) findViewById(R.id.show_count);
        mEditText = findViewById(R.id.editText_fib);

        n1 = 0;
        n2 = 1;
    }

showToast untuk menampilkan Toast dari button

    public void  showToast(View view){
        Toast toast = Toast.makeText(this, R.string.toast_message,
                Toast.LENGTH_SHORT);
        toast.show();
    }

#### Fungsi Menghitung Fibonacci (countUp)

    public void countUp(View view) { 
    }

Konversi integer ke String (karena Textview hanya menerima string)

    public void countUp(View view){
        int max = Integer.parseInt(mEditText.getText().toString());
    }

Munculkan toast jika sudah mencapai max

    public void countUp(View view) {

        int max = Integer.parseInt(mEditText.getText().toString());

        if (mCount >= max){
            Toast.makeText(this, R.string.toast_max_message, Toast.LENGTH_SHORT).show();
            return;
        }
    }

Code untuk Fibonacci

    public void countUp(View view) {

        int max = Integer.parseInt(mEditText.getText().toString());

        if (mCount >= max){
            Toast.makeText(this, R.string.toast_max_message, Toast.LENGTH_SHORT).show();
            return;

        int fib;
        if (mCount == 0){
            fib = 1;
        } else {
            fib = n1 + n2;
        }
        n2 = n1;
        n1 = fib;
        mCount++;
        
        mShowCount.setText(String.valueOf(n2));
        }
    }

#### Fungsi untuk kembali ke home

    public void countDown(View view){
        mCount = 1;
        n1 = 1;
        n2 = 0;
        mShowCount.setText(String.valueOf(n2));
    }

Hasilnya


https://github.com/alifamarta/PemogramanMobile-UTS/assets/115516820/52158903-00ec-44bf-9884-a0808a6fee7f
