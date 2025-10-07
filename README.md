def merge_sort(arr, key):
    if len(arr) > 1:
        mid = len(arr) // 2
        left_half = arr[:mid]
        right_half = arr[mid:]

        merge_sort(left_half, key)
        merge_sort(right_half, key)

        i = j = k = 0

    
        while i < len(left_half) and j < len(right_half):
            if left_half[i][key] < right_half[j][key]:
                arr[k] = left_half[i]
                i += 1
            else:
                arr[k] = right_half[j]
                j += 1
            k += 1

        while i < len(left_half):
            arr[k] = left_half[i]
            i += 1
            k += 1

        while j < len(right_half):
            arr[k] = right_half[j]
            j += 1
            k += 1


movies = [
    {"title": "Inception", "rating": 8.8, "year": 2010},
    {"title": "Avengers: Endgame", "rating": 8.4, "year": 2019},
    {"title": "The Dark Knight", "rating": 9.0, "year": 2008},
    {"title": "Interstellar", "rating": 8.6, "year": 2014},
    {"title": "Parasite", "rating": 8.6, "year": 2019},
]

print("Original Movie List:")
for m in movies:
    print(m)

merge_sort(movies, "rating")

print("\nSorted Movies by Rating:")
for m in movies:
    print(f"{m['title']} - {m['rating']} ({m['year']})")




