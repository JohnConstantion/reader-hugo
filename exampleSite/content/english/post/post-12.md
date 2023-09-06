---
title: "ARTS 打卡"
date: 2023-09-04T11:02:24+06:00
# post thumb
images:
  - "images/blog/arts.jpg"
#author
author: "Crucio"
# description
description: "This is meta description"
# Taxonomies
categories: [ "plan","arts" ]
tags: [ "arts","plan" ]
type: "regular" # available type (epic, trending, popular, or regular)
draft: false
---

## 1.Algorithm 做一道算法题
### 题目：两数之和
> 给定一个整数数组 nums 和一个整数目标值 target，请你在该数组中找出 和为目标值 target  的那 两个 整数，并返回它们的数组下标。
你可以假设每种输入只会对应一个答案。但是，数组中同一个元素在答案里不能重复出现。
你可以按任意顺序返回答案。
> 示例 1：
输入：nums = [2,7,11,15], target = 9
输出：[0,1]
解释：因为 nums[0] + nums[1] == 9 ，返回 [0, 1] 。
示例 2：
输入：nums = [3,2,4], target = 6
输出：[1,2]
示例 3：
输入：nums = [3,3], target = 6
输出：[0,1]

### 解题：
#### 暴力枚举
```java
class Solution {
     public int[] twoSum(int[] nums, int target) {
        for (int i = 0; i < nums.length; i++) {
            for (int j = i + 1; j < nums.length; j++) {
                if (target == (nums[i] + nums[j])) {
                    return new int[]{i, j};
                }
            }
        }
        return new int[0];
    }
}
```
#### 哈希表
```java
class Solution {
     public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> hashtable = new HashMap<Integer, Integer>();
        for (int i = 0; i < nums.length; i++) {
            if (hashtable.containsKey(target - nums[i])){
                return new int[]{hashtable.get(target - nums[i]), i};
            }
            hashtable.put(nums[i], i);
        }
        return new int[0];
    }
}
```
> 暴力枚举因为是两个循环在处理，有很大的可能是两个循环里的数据都要循环一遍，这就导致时间消耗的多，资源也被消耗了很多。
而哈希表的处理方式则是将筛选过的值放入到创建的hash表中，确保这个参数之后不会再进入循环中。这样可以循环到需要的值'或者'是整个循环结束没有对应的值。

## 2.Review 阅读一篇英文技术文章
I have this friend who considers himself a professional in his field. When he encounters other professionals acting unprofessionally, he reacts with some reserved disgust, as well he should. I’m like that too. Everyone I care to know is like that, because it’s a sign of pride; frustration at a peer acting carelessly, with no respect for the art you both work in, is a sign you Give A Shit.

One of the things I Give A Shit about the most is telling stories effectively, and it’s frustrating to see so many people fail to do so. I’ve talked about it before, but for me, a lot of this comes down to the simple fact that everyone thinks they can tell a story.

The truth is that everyone can tell a story, much like anyone can become a musician or a doctor or whatever else they can imagine. There’s no elitism here; sure, certain elements of storytelling might come more naturally to someone for various reasons, but there’s no magic bloodline, no secret genetics that will make you a good storyteller. All you’ve got to do is work at it. Reserve the disgust for the lazy and unwilling, for the people who’ve got no respect for the art form. Kindness is the only thing you should extend to the beginners.

“I went to the store today” is a not story. “I went to the store today and on the way back, I got a flat tire,” is getting there, but it still isn’t quite a story. “I went to the store today and on the way back, I got a flat tire, and a guy pulled over like he was going to help me, then he shouted something I couldn’t make out and raced off, like something had spooked him,” is the beginnings of a story, and it might even be interesting. A story pops off when something happens that sparks the imagination.A story pops off when something happens that sparks the imagination.

As you learn to write, you’ve probably gone through this process yourself. As a five year old, you left it at “I went to the store today.” As you progress in life, you’re probably writing better, more sophisticated stuff. It’s not a linear progression — tonight I was reminded of some excellent writing I’d done, and I also stumbled across some work that made me wince — but you are, gradually, getting better. At the gym, you don’t have to lift one more pound every day, but hopefully, on average, weeks and months after you started, you’re lifting 10 pounds more here, 50 pounds more there.

When we write stories, we learn little tips and tricks and things that make our stories pop, and when I set out to write this piece, that was what I intended to write about, but in setting up how we get there, I inadvertently wrote an entire thing on “how to tell a story,” so this is that now.

As we develop, we start to avoid pitfalls without even thinking about them. A common mistake that bad writers make is that they try to keep things close to the chest, especially when it comes to horror. Misunderstanding that terror is the buildup to horror, and that you can’t have setup with no punchline or punchline with no setup, many of them elect to write so cryptically that the story itself becomes difficult to follow. When a story becomes so cryptic that nothing means anything, the story stops being interesting.

If you think my work has value and you want to help me out financially, that would be great because being disabled in America is expensive. I’m putting all this out there for free because hey, I used to be in poverty and couldn’t get by without government assistance; I know what it’s like not to have resources available to you that other people have in spades. I don’t believe people should be denied access to educational materials like these just because they’re poor. My hope is that those of you who are able to support are willing to help not just me, but the people who can’t afford a lot of access to other game design materials. If you’re able to help and you think this goal of providing access to people who need it is good, here’s how you can help me keep writing:
