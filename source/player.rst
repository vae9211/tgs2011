============
Player.lua
============

.. attention ::
    * Player.lua 是【tgs/NewScript】目录下的一个文件。区别于 函数Player_

玩家登录
---------------------------------------------------
  function OnUserStart(PlayP, ...);

玩家发言
---------------------------------------------------
  function OnUserSay(PlayP, ...); ...用参数arg[1]..arg[9]获取

玩家离线
---------------------------------------------------
  function OnUserEnd(PlayP, ...);

玩家切换装备
---------------------------------------------------
  function OnChangeWearItem(PlayP);

玩家输入框输入信息
---------------------------------------------------
  function OnInputString(CmdP, PlayP, ...); arg[1]是输入Id, arg[2]是输入字符

玩家确认门武信息
---------------------------------------------------
  function OnConfirmGuildMagic(PlayP, MagicData);
   return MagicData;   end; 以下表内容 支持修改返回
MagicData = {MagicType=0, Shape=0, EffectColor=0, Speed=0, Recovery=0, Accuracy=0, KeepRecovery=0, Avoid=0, DamageBody=0, DamageHead=0, DamageArm=0, DamageLeg=0, ArmorBody=0, ArmorHead=0, ArmorArm=0, ArmorLeg=0, OutPower=0, InPower=0, MagicPower=0, Life=0, };

物品掉落提示
---------------------------------------------------
  function OnDropItem(PlayP, DropOwnerName, ItemData);
   return ItemData --如果return 不带ItemData 就不修改   end ItemData = {Name= '', ViewName = '', Count = 1, Shape=1, Color = 1, Sex = 1, UpGrade= 0, AddType =0, Kind = 4, EquipSet=0, boNotExchange=false, boNotDrop=false} 返回的是表时 支持修改以下表内容 ItemData = {Count= 0, ItemId= 0, UpGrade= 0, AddType= 0, BoAddAttrib=0}
玩家操作菜单返回
---------------------------------------------------
  function OnGetResult(PlayP, ...);

玩家被杀死
---------------------------------------------------
  function OnKilled(PlayP, ...); arg[1]是种族字符串, arg[2]是凶手名字

玩家被点击
---------------------------------------------------
  function OnClick(PlayP, ...); arg[1]是点击字符串
   return --如果返回字符串 就是点击显示的 否则按照传递的显示   end;
玩家显示
---------------------------------------------------
  function OnShow(PlayP, ...); arg[1]显示的名字
   return --如果返回字符串 就改变了显示的名字   end;
门派被灭
---------------------------------------------------
  function OnGuildOver(PlayP, ...); arg[1]是门派名字

怪物死亡
---------------------------------------------------
  function OnMonsterDie(MopP, PlayP, ...); arg[1]是怪物真名

挑战完成
---------------------------------------------------
  function OnChallengOver(OwnerP, ChallengeP, ...); ChallengeP是挑战者 arg[1]是押金名字， arg[2]是押金数量

拾取物品提示
---------------------------------------------------
  function OnPickUpItem(PlayP, PlayName, ItemData);

改变武功
---------------------------------------------------
  function OnChangeMagic(MopP, PlayP, ...); arg[1]武功名字