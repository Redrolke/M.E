#include <iostream>
#include <vector>
#include <algorithm>

std::vector<int> decimalParaBinario(int numero) {
    std::vector<int> binario;

    if (numero == 0) {
        binario.push_back(0);
    } else {
        while (numero > 0) {
            binario.push_back(numero % 2); 
            numero /= 2; 
        }
    }

    std::reverse(binario.begin(), binario.end());

    return binario;
}

int main() {
    int numero;

    std::cout << "Qual número gostaria de converter para binário: ";
    std::cin >> numero;

    std::vector<int> binario = decimalParaBinario(numero);

    std::cout << "O número " << numero << " em binário é: ";
    for (int i = 0; i < binario.size(); ++i) {
        std::cout << binario[i];
    }
    std::cout << std::endl;

    return 0;
}
