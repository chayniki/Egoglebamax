#include <iostream>
#include <fstream>
#include <string>

int main() {
    std::string filename;
    std::cout << "Введите имя текстового файла: ";
    std::cin >> filename;

    std::ifstream input_file(filename);
    if (!input_file) {
        std::cerr << "Ошибка открытия файла!" << std::endl;
        return 1;
    }

    std::string output_filename = "копия_" + filename;
    std::ofstream output_file(output_filename);

    if (!output_file) {
        std::cerr << "Ошибка создания копии файла!" << std::endl;
        return 1;
    }

    char ch;
    while (input_file.get(ch)) {
        if (ch != ' ') {
            output_file << ch;
        }
    }

    input_file.close();
    output_file.close();

    std::cout << "Копия файла без пробелов успешно создана!" << std::endl;

    return 0;
}
