# 写干净的 if else 语句

> 原文:[https://www . geesforgeks . org/writing-clean-else-statements/](https://www.geeksforgeeks.org/writing-clean-else-statements/)

使用 if else 链一些时间看起来更复杂，这可以通过以小块编写代码来避免。条件语句的使用增加了代码的可读性等等。一个最佳实践应该是首先处理错误案例。下面显示的例子显示了如何处理错误情况和简化 if else 逻辑。

**示例 1:**
updateCache()-这是一种基于一些类级变量决定更新主数据库的方法。
updateBackupDb()-是更新数据库的方法。

使用这种 if else 更难调试和扩展现有函数中的任何功能。
**优化前**

```
// A simple method handling the data
// base operation related task
private void updateDb(boolean isForceUpdate) {

  // isUpdateReady is class level
  // variable
  if (isUpdateReady) {

    // isForceUpdate is argument variable
    // and based on this inner blocks is
    // executed
    if (isForceUpdate) {

      // isSynchCompleted is also class
      // level variable, based on its
      // true/false updateDbMain is called
      // here updateBackupDb is called
      // in both the cases
      if (isSynchCompleted) {
        updateDbMain(true);
        updateBackupDb(true);

      } else {
        updateDbMain(false);
        updateBackupDb(true);
      }
    } else {

      // execute this if isUpdateReady is
      // false i. e., this is dependent on
      // if condition
      updateCache(!isCacheEnabled);

      // end of second isForceUpdate block
    }

    // end of first if block
  }

  // end of method
}
```

观察结果:
在下面的代码中，布尔变量已经被识别，并且基于此
代码使用 if 和 return 语句被分成小块。
1。如果更新没有准备好，则不需要在方法
中输入，只需退出该方法即可。
2。同样，如果 force update boolean 为 false，则执行 if 语句
中的任务–更新缓存并从此方法返回。
3。在最后一步中，所有任务都完成了更新备份数据库和更新主数据库。
**优化后**

```
// A simple method handling the
// data base operation related
// task
private void updateDb(boolean isForceUpdate) {

  // If isUpdateReaday boolean is not
  // true then return from this method,
  // nothing was done in else block
  if (!isUpdateReady) 
    return;

  // Now if isForceUpdate boolean is
  // not true then only updating the
  // cache otherwise this block was
  // not called
  if (!isForceUpdate) {
    updateCache(!isCacheEnabled);
    return;
  }

  // After all above condition is not
  // full filled below code is executed
  // this backup method was called two
  // times thus calling only single time
  updateBackupDb(true);

  // main db is updated based on sync
  // completed method
  updateDbMain(isSynchCompleted ? true : false);
}
```

**注-** 以上优化版本主要考虑的是基于条件语句简化 if else。
这种简单代码块的好处是——对于下一个开发人员来说，调试/理解/扩展这种方法非常容易。

**示例 2:**
**通过已有 JAVA API 代码示例解释这一思路**
这段代码片段取自 Java Doc:-
[JDK 子串代码 JAVA API](https://zgrepcode.com/java/oracle/jdk-8u181/java/lang/string.java#L-1924)
**已有代码来自上面的 API——这写得很完美。**
**优化后**

```
public String substring(int beginIndex, int endIndex) {

  // My comment - Below are the example of
  // correct use of if else, checking
  // condition and returning from // methods,
  // this is not about throwing error ie
  // return or throw error or do something
  // else - the idea is braking if // else
  // chaining.
  if (beginIndex < 0) {
    throw new StringIndexOutOfBoundsException(beginIndex);
  }

  if (endIndex > value.length) {
    throw new StringIndexOutOfBoundsException(endIndex);
  }

  int subLen = endIndex - beginIndex;

  if (subLen < 0) {
    throw new StringIndexOutOfBoundsException(subLen);
  }
  return ((beginIndex == 0) && (endIndex == value.length))
      ? this
      : new String(value, beginIndex, subLen);
}
```

如果在修改上述逻辑后，任何人使用 if else，如下例所示，这将非常复杂，但最终会产生相同的结果，因此我不喜欢在优化前执行如下所示–

```
public String substring(int beginIndex, int endIndex) {

  if (beginIndex < 0) {
    throw new StringIndexOutOfBoundsException(beginIndex);
  } else {

    // Again why this else block is used,
    // this need not to write, see above
    // correct implementation
    if (endIndex > value.length) {
      throw new StringIndexOutOfBoundsException(endIndex);
    } else {

      // This else is also not required
      int subLen = endIndex - beginIndex;
      if (subLen < 0) {
        throw new StringIndexOutOfBoundsException(subLen);
      }
    }
    return ((beginIndex == 0) && (endIndex == value.length))
        ? this
        : new String(value, beginIndex, subLen);
  }
}
```

**在看到上面两个例子后，可以观察到错误处理是在输入方法时完成的。首先处理错误情况是一个很好的做法。**

**总的来说，if else 可以根据需要在小块中使用，这将消除代码复杂性，代码将易于使用/调试/维护/扩展。**