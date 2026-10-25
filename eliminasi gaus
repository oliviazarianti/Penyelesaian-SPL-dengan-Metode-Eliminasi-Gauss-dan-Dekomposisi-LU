import numpy as np
A = np.array([[3.0, 1.0, -4.0], [-2.0, 3.0, 1.0], [2.0, 0.0, 5.0]])

b = np.array([7.0, -5.0, 10.0])

def eliminasi_gauss(A, b):
  n = len(b)
  Ab = np.hstack([A, b.reshape(-1, 1)])

  print("=== Matriks Augmented Awal ===")
  print(Ab)
  print("=" * 45)


  for i in range(n):
   
    pivot = Ab[i, i]
    if abs(pivot) < 1e-12:
      print(f"Error: Pivot bernilai nol pada baris {i + 1}.")
      return None

   
    for j in range(i + 1, n):
      faktor = Ab[j, i] / Ab[i, i]
      Ab[j, i:] = Ab[j, i:] - faktor * Ab[i, i:]

    print(f"Setelah Eliminasi Kolom {i + 1}:")
    print(Ab)
    print("-" * 45)

  x = np.zeros(n)
  for i in range(n - 1, -1, -1):
    x[i] = (Ab[i, -1] - np.dot(Ab[i, i + 1 : n], x[i + 1 : n])) / Ab[i, i]

  return x

hasil_solusi = eliminasi_gauss(A, b)

if hasil_solusi is not None:
  print("\n=== Hasil Solusi Akhir ===")
  print(f"x1 = {hasil_solusi[0]:.4f}  (Pecahan: 260/81)")
  print(f"x2 = {hasil_solusi[1]:.4f}  (Pecahan: 19/81)")
  print(f"x3 = {hasil_solusi[2]:.4f}  (Pecahan: 58/81)")
