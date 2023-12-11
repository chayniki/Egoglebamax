#include <iostream>
#include <string>
#include <filesystem>

int main()
{

static std::filesystem::path my_path_from;
static std::filesystem::path my_path_to;

my_path_from = L"С:\\sprob\\";
my_path_to =   L"С:\\bezbrob\\2\\";


std::filesystem::copy_options my_options;
my_options = std::filesystem::copy_options::none;

try
{
std::filesystem::copy(my_path_from, my_path_to,.my_options);
}
catch(const std::filesystem::filesystem_error& e)
{
std::cout<< e.what()<<std::endl;   //Ошибки не отлавливаются, все завершается успешно.
}
}
