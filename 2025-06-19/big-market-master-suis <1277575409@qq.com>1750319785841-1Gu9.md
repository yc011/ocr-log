根据提供的 `git diff` 记录，以下是对代码变更的评审：

### 新增文件：IRaffleActivityService.java
- **优点**:
  - 新增了 `IRaffleActivityService` 接口，定义了两个方法：`armory` 和 `draw`，用于活动装配和活动抽奖。
  - `ActivityDrawRequestDTO` 和 `ActivityDrawResponseDTO` DTO 类被创建，用于封装抽奖请求和响应数据。
- **缺点**:
  - 接口和 DTO 类的注释信息不够详细，没有说明参数和返回值的含义。
  - 缺少异常处理机制，如果方法执行失败，需要定义相应的异常类型。

### 重命名文件：IRaffleService.java -> IRaffleStrategyService.java
- **优点**:
  - 将 `IRaffleService` 接口重命名为 `IRaffleStrategyService`，更准确地反映了接口的功能。
- **缺点**:
  - 重命名可能需要修改其他地方的代码引用，需要确保所有相关代码都进行了相应的更新。

### 修改文件：RaffleRequestDTO.java -> RaffleStrategyRequestDTO.java
- **优点**:
  - 将 `RaffleRequestDTO` 类重命名为 `RaffleStrategyRequestDTO`，与接口名称保持一致。
- **缺点**:
  - 与上面的重命名一样，可能需要修改其他地方的代码引用。

### 修改文件：RaffleResponseDTO.java -> RaffleStrategyResponseDTO.java
- **优点**:
  - 与上面的重命名一样，与接口名称保持一致。
- **缺点**:
  - 与上面的重命名一样，可能需要修改其他地方的代码引用。

### 修改文件：RaffleActivityMapper.xml
- **优点**:
  - 新增了两个查询语句，用于根据活动ID查询策略ID和根据策略ID查询活动ID。
- **缺点**:
  - 没有添加异常处理机制，如果查询失败，需要定义相应的异常类型。

### 修改文件：UserRaffleOrderMapper.xml
- **优点**:
  - 新增了更新用户抽奖订单状态的语句，将订单状态从“创建”更新为“已使用”。
- **缺点**:
  - 与上面的修改一样，没有添加异常处理机制。

### 修改文件：PartakeRaffleActivityEntity.java
- **优点**:
  - 添加了 `@Builder`、`@AllArgsConstructor` 和 `@NoArgsConstructor` 注解，方便创建对象实例。
- **缺点**:
  - 没有添加字段注释，不便于理解字段含义。

### 修改文件：IRaffleActivityPartakeService.java
- **优点**:
  - 添加了 `createOrder` 方法，用于创建抽奖订单。
- **缺点**:
  - 没有添加异常处理机制。

### 修改文件：ActivityArmory.java
- **优点**:
  - 添加了 `assembleActivitySkuByActivityId` 方法，用于根据活动ID装配活动SKU。
- **缺点**:
  - 没有添加异常处理机制。

### 修改文件：IActivityArmory.java
- **优点**:
  - 添加了 `assembleActivitySkuByActivityId` 方法。
- **缺点**:
  - 与上面的修改一样，没有添加异常处理机制。

### 修改文件：AbstractRaffleActivityPartake.java
- **优点**:
  - 添加了 `createOrder` 方法，用于创建抽奖订单。
- **缺点**:
  - 与上面的修改一样，没有添加异常处理机制。

### 修改文件：RaffleAwardEntity.java
- **优点**:
  - 添加了 `awardTitle` 字段，用于存储奖品标题。
- **缺点**:
  - 没有添加字段注释，不便于理解字段含义。

### 修改文件：IStrategyRepository.java
- **优点**:
  - 添加了 `queryStrategyIdByActivityId` 和 `queryTodayUserRaffleCount` 方法，用于查询策略ID和用户抽奖次数。
- **缺点**:
  - 与上面的修改一样，没有添加异常处理机制。

### 修改文件：AbstractRaffleStrategy.java
- **优点**:
  - 添加了 `awardTitle` 字段，用于存储奖品标题。
- **缺点**:
  - 与上面的修改一样，没有添加字段注释，不便于理解字段含义。

### 修改文件：IStrategyArmory.java
- **优点**:
  - 添加了 `assembleLotteryStrategyByActivityId` 方法，用于根据活动ID装配抽奖策略配置。
- **缺点**:
  - 与上面的修改一样，没有添加异常处理机制。

### 修改文件：StrategyArmoryDispatch.java
- **优点**:
  - 添加了 `assembleLotteryStrategyByActivityId` 方法，用于根据活动ID装配抽奖策略配置