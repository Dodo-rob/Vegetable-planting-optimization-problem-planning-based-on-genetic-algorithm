code intriduction: <br> 
1.通过遗传算法基础算法加上惩罚函数(约束条件)算法确定最优基因，根据基因绘制热力图查看分布。<br> 
2.根据最优的基因序列，计算不同作物在同一块地上的利润占比分配各自作物的种植面积。<br> 

************Genetic_algorithm_updata.py************ <br>

Genetic_algorithm_updata:主要的运行文件 <br> 
def __init__ :<br>
        :param costs: 作物种植成本的列表<br>
        :param prices: 各年作物价格的列表<br>
        :param yields: 各年作物亩产量的列表<br>
        :param area: 各地块面积的列表<br>
        :param area_mode: 地块数量<br>
        :param crop_type: 作物数量<br>
        :param year: 年份数量<br>
        :param population_size: 种群大小<br>
        :param number_iterations: 迭代次数<br>
        :param probability_variation: 变异概率<br>
        :param choose_min: 选择最少作物<br>
        :param choose_max: 选择最多作物<br>
def initialize_population :初始化种群结构<br>
        :param pop_size: 种群大小<br>
        :return: 初始化后的种群<br>
def calculate_penalty : 计算正态分布惩罚函数<br>
        :param individual: 个体解决方案<br>
        :param front_plots: 分块1<br>
        :param middle_plots: 分块2<br>
        :param end_plots: 分块3 <br>
        :return: penalty 惩罚值<br>
def at_least_one_crop : 每块地至少种一种作物的惩罚函数<br>
def up_to_n_crops : 每块地每年最多种三种作物的惩罚函数<br>
def fitness : 计算个体的适应度：总利润减去惩罚<br>
        :param individual: 个体解决方案<br>
        :param a: 销量占产量系数初始化<br>
        :param b: 增收因子<br>
        :return: 适应度值<br>
def selection : 选择适应度最高的个体<br>
def crossover : 交叉操作，生成两个子代个体<br>
def mutate : 变异操作：随机改变个体<br>
def run_genetic_algorith : 运行遗传算法并返回最佳个体<br>

********************Excel_deal.py********************<br>

def read_and_extract_data : 从指定的 Excel 文件中读取指定列，并从指定行范围内提取数据。<br>
    :param file_path: Excel 文件的路径<br>
    :param usecols: 需要读取的列的索引列表<br>
    :param start_row: 读取数据的起始行（基于 0 索引）<br>
    :param end_row: 读取数据的结束行（包含 end_row 行）<br>
    :return costs: 第一列的数据（成本）<br>
    :return prices: 第2到第8列的数据（价格）<br>
    :return yields: 第9到第15列的数据（亩产量）<br>
def delete_sheet :删除重复表头<br>
def save_all_data_to_excel_by_year : 将每一年每个作物的种植面积分配数据保存到 Excel 文件中。<br>
    :param file_path: str, Excel 文件路径。<br>
    :param optimal_solution: np.array, 最优解矩阵，包含每个地块每年每种作物的分配决策。<br>
    :param areas: list, 每个地块的总面积。<br>
    :param area_mode: int, 表示土地模式的数量（即多少个地块）。<br>
    :param year: int, 总的种植年份数。<br>
    :param crop_type: int, 作物种类的数量。<br>
    :param prices: list, 各年份每种作物的价格。<br>
    :param yields: list, 各年份每种作物的亩产量。<br>
    :param costs: list, 每种作物的种植成本。<br>

 ********************J.xlsx********************<br>

    试运行文件
