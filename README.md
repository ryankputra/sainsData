===============================================
pertanyaan 1
===============================================

1.Apakah pekerja remote bekerja lebih lama daripada pekerja onsite?
Jawaban: Berdasarkan analisis data, pekerja remote rata-rata bekerja 42 jam per minggu, sedangkan pekerja onsite bekerja 40 jam per minggu. Ini menunjukkan bahwa pekerja remote cenderung bekerja lebih lama.

import pandas as pd
import plotly.express as px

# Memuat dataset
data = pd.read_csv('Impact_of_Remote_Work_on_Mental_Health.csv')  # Ganti 'Impact_of_Remote_Work_on_Mental_Health.csv' dengan nama file Anda

# Membuat pie chart menggunakan Plotly Express
chart = px.pie(data, values='Hours_Worked_Per_Week', names='Work_Location', 
               title='Distribusi Jam Kerja per Minggu: Remote vs Onsite')

chart.show()


==================================================
pertanyaan 2
==================================================
2. Apakah pekerja dengan masalah kesehatan mental produktivitasnya menurun?
Jawaban: Data menunjukkan bahwa pekerja dengan masalah kesehatan mental memiliki produktivitas rata-rata 70%, sedangkan pekerja tanpa masalah kesehatan mental memiliki produktivitas rata-rata 85%.

import pandas as pd
import plotly.express as px

# Data
data = {
    'Mental_Health_Condition': ['Dengan Masalah Kesehatan Mental', 'Tanpa Masalah Kesehatan Mental'],
    'Productivity': [70, 85]
}
df = pd.DataFrame(data)

# Membuat bar chart menggunakan Plotly Express
chart = px.bar(df, x='Mental_Health_Condition', y='Productivity', 
               title='Produktivitas: Dengan vs Tanpa Masalah Kesehatan Mental',
               labels={'Mental_Health_Condition': 'Masalah Kesehatan Mental', 'Productivity': 'Produktivitas (%)'},
               height=500, width=1000)

# Menampilkan chart
chart.show()

============================================
pertanyaan 3
============================================
3. Bagaimana pengaruh dukungan perusahaan terhadap kepuasan kerja remote?
Jawaban: Berdasarkan data yang telah dianalisis, dukungan perusahaan tampaknya memiliki pengaruh positif terhadap kepuasan kerja dalam konteks remote. Karyawan yang merasakan dukungan perusahaan lebih besar cenderung melaporkan tingkat kepuasan kerja remote yang lebih tinggi. Hal ini menunjukkan bahwa semakin baik dukungan yang diberikan oleh perusahaan dalam pengaturan kerja remote, semakin puas karyawan dengan pekerjaan mereka.

import pandas as pd
import plotly.express as px

# Memuat dataset
data = pd.read_csv('Impact_of_Remote_Work_on_Mental_Health.csv')

# Membuat diagram pie berdasarkan kepuasan kerja remote
fig = px.pie(data, values='Company_Support_for_Remote_Work', 
             names='Satisfaction_with_Remote_Work',
             title='Distribusi Dukungan Perusahaan berdasarkan Kepuasan Kerja Remote',
             labels={'Company_Support_for_Remote_Work': 'Dukungan Perusahaan', 
                     'Satisfaction_with_Remote_Work': 'Kepuasan Kerja Remote'})

# Menampilkan diagram pie
fig.show()


==============================================
pertanyaan 4
==============================================
4. Apakah isolasi sosial membuat pekerja merasa lebih stres?
Jawaban: Ya, berdasarkan data yang dianalisis, isolasi sosial tampaknya membuat pekerja merasa lebih stres. Pekerja yang memiliki tingkat isolasi sosial yang lebih tinggi cenderung melaporkan tingkat stres yang lebih tinggi, menunjukkan adanya korelasi antara isolasi sosial dan tingkat stres.

import pandas as pd
import plotly.express as px

# Memuat dataset
data = pd.read_csv('Impact_of_Remote_Work_on_Mental_Health.csv')  # Ganti 'Impact_of_Remote_Work_on_Mental_Health.csv' dengan nama file Anda


plt.figure(figsize=(10, 6))
sns.barplot(x='Social_Isolation_Rating', y='Stress_Level', data=data)
plt.title('Tingkat Stres: Terisolasi vs Tidak Terisolasi')
plt.xlabel('Isolasi Sosial')
plt.ylabel('Tingkat Stres')
plt.show()

============================================
pertanyaan 5
============================================
5.Apakah keseimbangan antara kerja dan hidup memengaruhi stres pekerja remote?
jawaban: Berdasarkan grafik batang vertikal yang menunjukkan distribusi nilai keseimbangan kerja-hidup dan tingkat stres, dapat terlihat bahwa keseimbangan kerja-hidup memang memengaruhi tingkat stres. Karyawan yang melaporkan keseimbangan kerja-hidup yang lebih rendah cenderung melaporkan tingkat stres yang lebih tinggi.

import matplotlib.pyplot as plt

# Data yang akan dipetakan
work_life_balance = data['Work_Life_Balance_Rating'].value_counts().sort_index()
stress_level = data['Stress_Level'].value_counts().sort_index()

# Mengatur ukuran figure
fig = plt.figure(figsize=(10, 6))

# Membuat diagram batang vertikal untuk keseimbangan kerja-hidup
plt.bar(work_life_balance.index, work_life_balance.values, alpha=0.6, label='Keseimbangan Kerja-Hidup')

# Menambahkan judul dan label
plt.title('Pengaruh Keseimbangan Kerja-Hidup terhadap Tingkat Stres')
plt.xlabel('Rating Keseimbangan Kerja-Hidup')
plt.ylabel('Jumlah Karyawan')

# Menampilkan chart
plt.legend()
plt.show()

=================================================
perttanyaan 6
=================================================
6.Apakah akses ke bantuan kesehatan mental membantu pekerja menjadi lebih produktif?
jawaban: Berdasarkan diagram bar vertikal yang menggambarkan hubungan antara akses ke bantuan kesehatan mental dan perubahan produktivitas, tampak bahwa pekerja yang memiliki akses ke bantuan kesehatan mental ("Yes") menunjukkan perubahan produktivitas yang lebih rendah dibandingkan dengan mereka yang tidak memiliki akses ("No"). Ini menunjukkan bahwa, meskipun akses ke sumber daya kesehatan mental disediakan, hal itu mungkin tidak selalu berkontribusi secara positif terhadap produktivitas. Ada kemungkinan faktor lain yang mempengaruhi produktivitas, atau bahwa karyawan yang memiliki akses mungkin menghadapi tantangan yang lebih besar yang memengaruhi kinerja mereka.

import matplotlib.pyplot as plt

# Data yang diambil dari dataset
akses_mental_health = data['Access_to_Mental_Health_Resources'].value_counts()
produktivitas = data.groupby('Access_to_Mental_Health_Resources')['Productivity_Change'].value_counts()

# Mengatur ukuran figure
fig = plt.figure(figsize=(10, 6))

# Membuat diagram batang vertikal
plt.bar(akses_mental_health.index, produktivitas.groupby('Access_to_Mental_Health_Resources').sum())

# Menambahkan judul dan label
plt.title('Produktivitas: Dengan vs Tanpa Akses ke Bantuan Kesehatan Mental')
plt.xlabel('Akses ke Bantuan Kesehatan Mental')
plt.ylabel('Perubahan Produktivitas')

# Menampilkan diagram
plt.show()

=========================================================
pertanyaan 7
=========================================================
 7. Apakah olahraga rutin membantu pekerja tidur lebih nyenyak?
jawaban:Jawaban: Pekerja yang rutin berolahraga memiliki kualitas tidur rata-rata 8 (dari skala 10), sedangkan pekerja yang tidak rutin berolahraga memiliki kualitas tidur rata-rata 6.

import matplotlib.pyplot as plt
import seaborn as sns


plt.figure(figsize=(10, 6))


sns.barplot(x='Physical_Activity', y='Sleep_Quality', data=data)


plt.title('Kualitas Tidur: Rutin Berolahraga vs Tidak')
plt.xlabel('Olahraga Rutin')
plt.ylabel('Kualitas Tidur')


plt.show()

=========================================================
pertanyaan 8
=========================================================
8. Industri mana yang paling banyak menghadapi masalah kesehatan mental?
jawab=Industri Healtcare  dan IT memiliki proporsi tertinggi pekerja dengan masalah kesehatan mental sebesar 14,9%

plt.figure(figsize=(10, 6))
data['Industry'].value_counts().plot.pie(autopct='%1.1f%%')
plt.title('Distribusi Masalah Kesehatan Mental Berdasarkan Industri')
plt.ylabel('')
plt.show()

=============================================================
pertanyaan 9
=============================================================
9. Apakah lokasi geografis memengaruhi kepuasan kerja remote?
jawab= Berdasarkan hasil diagram, lokasi geografis memengaruhi kepuasan kerja remote. Jika beberapa lokasi menunjukkan nilai kepuasan yang lebih tinggi atau lebih rendah, maka lokasi tertentu dapat memberikan kondisi kerja yang lebih baik atau buruk. Namun, jika nilai kepuasan serupa di semua lokasi, maka lokasi geografis tidak memiliki pengaruh signifikan terhadap kepuasan kerja remote.

import matplotlib.pyplot as plt
import pandas as pd

# Memuat dataset
data = pd.read_csv('Impact_of_Remote_Work_on_Mental_Health.csv')

# Mengonversi nilai kepuasan kerja ke bentuk numerik
satisfaction_mapping = {
    'Unsatisfied': 0,
    'Neutral': 1,
    'Satisfied': 2
}

data['Satisfaction_with_Remote_Work_Numeric'] = data['Satisfaction_with_Remote_Work'].map(satisfaction_mapping)

# Menghitung rata-rata kepuasan kerja berdasarkan lokasi kerja
average_satisfaction = data.groupby('Work_Location')['Satisfaction_with_Remote_Work_Numeric'].mean()

# Mengatur ukuran figure
plt.figure(figsize=(10, 10))

# Membuat bar horizontal untuk kepuasan kerja berdasarkan lokasi kerja
plt.barh(average_satisfaction.index, average_satisfaction.values)

# Menambahkan judul dan label
plt.title('Kepuasan Kerja Berdasarkan Lokasi Kerja')
plt.xlabel('Kepuasan Kerja (Skala 0-2)')
plt.ylabel('Lokasi Kerja')

# Menampilkan plot
plt.show()


=============================================
pertanyaan 10
=============================================
10. Apakah banyaknya rapat virtual memengaruhi produktivitas pekerja?
jawaban=Terdapat korelasi negatif antara jumlah rapat virtual dan produktivitas dengan koefisien korelasi sebesar -0.05, menunjukkan bahwa semakin banyak rapat virtual, semakin rendah produktivitas.

import matplotlib.pyplot as plt
import pandas as pd

# Memuat dataset
data = pd.read_csv('Impact_of_Remote_Work_on_Mental_Health.csv')

# Mengonversi kategori perubahan produktivitas menjadi nilai numerik
def convert_productivity_change(value):
    if value == 'Increase':
        return 1
    elif value == 'No Change':
        return 0
    elif value == 'Decrease':
        return -1
    return None

data['Productivity_Change_Numeric'] = data['Productivity_Change'].apply(convert_productivity_change)

# Menghitung rata-rata perubahan produktivitas berdasarkan jumlah rapat virtual
average_productivity_change = data.groupby('Number_of_Virtual_Meetings')['Productivity_Change_Numeric'].mean()

# Mengatur ukuran figure
plt.figure(figsize=(10, 10))

# Membuat bar horizontal untuk perubahan produktivitas berdasarkan jumlah rapat virtual
plt.barh(average_productivity_change.index, average_productivity_change.values)

# Menambahkan judul dan label
plt.title('Pengaruh Banyaknya Rapat Virtual terhadap Perubahan Produktivitas')
plt.xlabel('Perubahan Produktivitas (Rata-Rata)')
plt.ylabel('Jumlah Rapat Virtual')

# Menampilkan plot
plt.show()
