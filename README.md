# Python_Patika
1- Bir listeyi düzleştiren (flatten) fonksiyon yazın. Elemanları birden çok katmanlı listelerden ([[3],2] gibi) oluşabileceği gibi, non-scalar verilerden de oluşabilir. Örnek olarak:

input: [[1,'a',['cat'],2],[[[3]],'dog'],4,5]

output: [1,'a','cat',2,3,'dog',4,5]

def flatten_list(nested_list):
    flat_list = []
    
    def flatten(sublist):
        for item in sublist:
            if isinstance(item, list):
                flatten(item)      
            else:
                flat_list.append(item)  
    flatten(nested_list)  
    return flat_list  

# Örnek kullanım

input_list = [[1, 'a', ['cat'], 2], [[[3]], 'dog'], 4, 5]

output_list = flatten_list(input_list)

print(output_list)  




2- Verilen listenin içindeki elemanları tersine döndüren bir fonksiyon yazın. Eğer listenin içindeki elemanlar da liste içeriyorsa onların elemanlarını da tersine döndürün. Örnek olarak:

input: [[1, 2], [3, 4], [5, 6, 7]]

output: [[[7, 6, 5], [4, 3], [2, 1]]


def reverse_nested_list(nested_list):
   
    def reverse_list(lst):
        reversed_list = []
        for item in reversed(lst): 
            if isinstance(item, list):
                reversed_list.append(reverse_list(item))  
            else:
                reversed_list.append(item)
        return reversed_list

    return reverse_list(nested_list)



# Örnek kullanım

input_list = [[1, 2], [3, 4], [5, 6, 7]]

output_list = reverse_nested_list(input_list)

print(output_list)  
