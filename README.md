*************Genetic_algorithm_updata.py************
Genetic_algorithm_updata:The main running script of the genetic algorithm
def __init__ :
        :param costs: 作物种植成本的列表
        :param prices: 各年作物价格的列表
        :param yields: 各年作物亩产量的列表
        :param area: 各地块面积的列表
        :param area_mode: 地块数量
        :param crop_type: 作物数量
        :param year: 年份数量
        :param population_size: 种群大小
        :param number_iterations: 迭代次数
        :param probability_variation: 变异概率
        :param choose_min: 选择最少作物
        :param choose_max: 选择最多作物
def initialize_population :初始化种群结构
        :param pop_size: 种群大小
        :return: 初始化后的种群
def calculate_penalty : 计算正态分布惩罚函数
        :param individual: 个体解决方案
        :param front_plots: 分块1
        :param middle_plots: 分块2
        :param end_plots: 分块3 
        :return: penalty 惩罚值
def at_least_one_crop : 每块地至少种一种作物的惩罚函数
def up_to_n_crops : 每块地每年最多种三种作物的惩罚函数
def fitness : 计算个体的适应度：总利润减去惩罚
        :param individual: 个体解决方案
        :param a: 销量占产量系数初始化
        :param b: 增收因子
        :return: 适应度值
def selection : 选择适应度最高的个体
def crossover : 交叉操作，生成两个子代个体
def mutate : 变异操作：随机改变个体
def run_genetic_algorith : 运行遗传算法并返回最佳个体
********************Excel_deal.py********************
def read_and_extract_data : 从指定的 Excel 文件中读取指定列，并从指定行范围内提取数据。
    :param file_path: Excel 文件的路径
    :param usecols: 需要读取的列的索引列表
    :param start_row: 读取数据的起始行（基于 0 索引）
    :param end_row: 读取数据的结束行（包含 end_row 行）
    :return costs: 第一列的数据（成本）
    :return prices: 第2到第8列的数据（价格）
    :return yields: 第9到第15列的数据（亩产量）
def delete_sheet :删除重复表头
def save_all_data_to_excel_by_year : 将每一年每个作物的种植面积分配数据保存到 Excel 文件中。
    :param file_path: str, Excel 文件路径。
    :param optimal_solution: np.array, 最优解矩阵，包含每个地块每年每种作物的分配决策。
    :param areas: list, 每个地块的总面积。
    :param area_mode: int, 表示土地模式的数量（即多少个地块）。
    :param year: int, 总的种植年份数。
    :param crop_type: int, 作物种类的数量。
    :param prices: list, 各年份每种作物的价格。
    :param yields: list, 各年份每种作物的亩产量。
    :param costs: list, 每种作物的种植成本。
    ********************J.xlsx********************
    试运行文件
