### <a name="change-in-behavior-in-data-definition-language-ddl-apis"></a><span data-ttu-id="534b4-101">数据定义语言 (DDL) API 行为的更改</span><span class="sxs-lookup"><span data-stu-id="534b4-101">Change in behavior in Data Definition Language (DDL) APIs</span></span>

|   |   |
|---|---|
|<span data-ttu-id="534b4-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="534b4-102">Details</span></span>|<span data-ttu-id="534b4-103">指定 AttachDBFilename 时，DDL API 的行为已更改，具体如下：</span><span class="sxs-lookup"><span data-stu-id="534b4-103">The behavior of DDL APIs when AttachDBFilename is specified has changed as follows:</span></span><ul><li><span data-ttu-id="534b4-104">连接字符串不需要指定 Initial Catalog 值。</span><span class="sxs-lookup"><span data-stu-id="534b4-104">Connection strings need not specify an Initial Catalog value.</span></span> <span data-ttu-id="534b4-105">以前，需要 AttachDBFilename 和 Initial Catalog。</span><span class="sxs-lookup"><span data-stu-id="534b4-105">Previously, both AttachDBFilename and Initial Catalog were required.</span></span></li><li><span data-ttu-id="534b4-106">如果指定了 AttachDBFilename 和 Initial Catalog，并且存在给定的 MDF 文件，ObjectContext.DatabaseExists 方法将返回 true。</span><span class="sxs-lookup"><span data-stu-id="534b4-106">If both AttachDBFilename and Initial Catalog are specified and the given MDF file exists, the ObjectContext.DatabaseExists method returns true.</span></span> <span data-ttu-id="534b4-107">以前，它会返回 false。</span><span class="sxs-lookup"><span data-stu-id="534b4-107">Previously, it returned false.</span></span></li><li><span data-ttu-id="534b4-108">如果指定了 AttachDBFilename 和 Initial Catalog，并且存在给定的 MDF 文件，则调用 ObjectContext.DeleteDatabase 方法会删除文件。</span><span class="sxs-lookup"><span data-stu-id="534b4-108">If both AttachDBFilename and Initial Catalog are specified and the given MDF file exists, calling the ObjectContext.DeleteDatabase method deletes the files.</span></span></li><li><span data-ttu-id="534b4-109">如果在连接字符串指定某个 AttachDBFilename 值，且不存在 MDF 和 Initial Catalog 时调用 ObjectContext.DeleteDatabase，该方法将引发 InvalidOperationException 异常。</span><span class="sxs-lookup"><span data-stu-id="534b4-109">If ObjectContext.DeleteDatabase is called when the connection string specifies an AttachDBFilename value with an MDF that doesn't exist and an Initial Catalog that doesn't exist, the method throws an InvalidOperationException exception.</span></span> <span data-ttu-id="534b4-110">以前，它会引发 SqlException 异常。</span><span class="sxs-lookup"><span data-stu-id="534b4-110">Previously, it threw a SqlException exception.</span></span></li></ul>|
|<span data-ttu-id="534b4-111">建议</span><span class="sxs-lookup"><span data-stu-id="534b4-111">Suggestion</span></span>|<span data-ttu-id="534b4-112">利用这些更改，可以更轻松地生成使用 DDL API 的工具和应用程序。</span><span class="sxs-lookup"><span data-stu-id="534b4-112">These changes make it easier to build tools and applications that use the DDL APIs.</span></span> <span data-ttu-id="534b4-113">这些更改会影响以下方案中的应用程序兼容性：</span><span class="sxs-lookup"><span data-stu-id="534b4-113">These changes can affect application compatibility in the following scenarios:</span></span><ul><li><span data-ttu-id="534b4-114">如果 ObjectContext.DatabaseExists 返回 true，用户将编写直接执行 DROP DATABASE 命令的代码，而不是调用 ObjectContext.DeleteDatabase。</span><span class="sxs-lookup"><span data-stu-id="534b4-114">The user writes code that executes a DROP DATABASE command directly instead of calling ObjectContext.DeleteDatabase if ObjectContext.DatabaseExists returns true.</span></span> <span data-ttu-id="534b4-115">如果未附加数据库但存在 MDF 文件，则会中断现有代码。</span><span class="sxs-lookup"><span data-stu-id="534b4-115">This breaks existing code If the database is not attached but the MDF file exists.</span></span></li><li><span data-ttu-id="534b4-116">用户编写希望 ObjectContext.DeleteDatabase 方法在 Initial Catalog 和 MDF 文件不存在时引发 SqlException 异常而非 InvalidOperationException 异常的代码。</span><span class="sxs-lookup"><span data-stu-id="534b4-116">The user writes code that expects the ObjectContext.DeleteDatabase method to throw a SqlException exception rather than an InvalidOperationException exception when the Initial Catalog and MDF file don't exist.</span></span></li></ul>|
|<span data-ttu-id="534b4-117">范围</span><span class="sxs-lookup"><span data-stu-id="534b4-117">Scope</span></span>|<span data-ttu-id="534b4-118">次要</span><span class="sxs-lookup"><span data-stu-id="534b4-118">Minor</span></span>|
|<span data-ttu-id="534b4-119">版本</span><span class="sxs-lookup"><span data-stu-id="534b4-119">Version</span></span>|<span data-ttu-id="534b4-120">4.5</span><span class="sxs-lookup"><span data-stu-id="534b4-120">4.5</span></span>|
|<span data-ttu-id="534b4-121">类型</span><span class="sxs-lookup"><span data-stu-id="534b4-121">Type</span></span>|<span data-ttu-id="534b4-122">运行时</span><span class="sxs-lookup"><span data-stu-id="534b4-122">Runtime</span></span>|
