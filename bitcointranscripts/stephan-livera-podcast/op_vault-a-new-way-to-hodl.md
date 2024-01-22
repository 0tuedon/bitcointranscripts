---
title: "OP_Vault - A New Way to HODL?"
transcript_by: 0tuedon via review.btctranscripts.com
media: https://www.youtube.com/watch?v=Nq6WxJ0PgJ4
tags: ["op_vault"]
speakers: ["Stephan Livera","James O’Beirne"]
categories: ["podcast"]
date: 2023-01-30
---

James welcome back to the show.
Ace of funds great to be back.
I think it's been almost four years, huh?
Damn.

So I think everybody knows that custody in Bitcoin is really hard and pretty much  everybody's major fear on Bitcoin is waking up one day and you know,  checking your wallet and seeing that somebody's gotten away with your coins.
And so a lot of thought has been put into, you know,  things that can mitigate the risk of losing your coins.
And especially kind of having experienced an industrial custody context  at a few different places.
There's been an idea circulating for a while of this notion of a vault.
And the idea of a vault is basically that you can walk up the coins in such a way  that if you want to move them in general,  you have to wait for this delay period and during the delay period.
You can kind of contest the spend aside from spending the coins into a  pre-specified recovery path.
And so I think the first time that vaults were really discussed was in a paper.
I want to say in 2014 or 2015, it's paper called Bitcoin Covenants,  written by Moser, Yael, and Eamon Gunseer.
And it's kind of an interesting paper because they formalized sort of the notion  of Bitcoin Covenants, which had been kind of mentioned by Greg Maxwell in a Bitcoin talk post  back in 2013 in actually a very derogatory context.
But these guys form wise it into a paper sort of, and it's a weird paper because  they spend the first half talking about vaults and then like the second half talking about how  they can repurpose this covenant stuff to make Bitcoin and G.
But it's worth a read if you're  interested in vaults.
So anyway, they sort of discussed in the abstract this idea of how you could  put a constraint on not only just unlocking a coin and spending it to some arbitrary destination,  but you could put constraints on how the coins actually spend.
And then you could use that to  reify this idea of a vault.
So let's just take one step, just to make sure everyone's following  along, right?
Because I think I'm following you and I think you obviously you understand this,  but just make sure listen is a following along.
Let me put it this way, you correct me if I'm getting this wrong, but the basic idea is when you  have a like probably probably people who used to this idea of sending Bitcoin from one address to  another, but really what's going on kind of under the hood is that address is it can contain a script  and you can think of it like we're locking coins into a certain script and we need certain conditions  to unlock that coin and spend it somewhere else.
And so what we're talking about here is like using  script in a special way to create this special vault construction that gives us maybe a little bit more  confidence about if something would happen that I could then  stop the theft of my coins.
Let's say to buy pulling them into a different recovery  address.
Let's say is that high level what we're talking about?
Yeah, that's exactly right.
Just to restate, you know, when you're sending your coins somewhere,  quote unquote, what you're really doing is you're spending a coin, which involves presenting  a proof or an input to basically a little computer program that have locked the coins  and that input gets fed into that computer program, the Bitcoin script engine executes that program  with the inputs, the inputs are now called witnesses.
And then if that execution succeeds, then  you can basically lock the value up with another computer program.
And in Bitcoin today right now,  if you successfully unlock that first computer program, you can pretty much spend the coins  in whatever way that you want.
But this idea of covenants is that, okay, maybe you're presenting  well, you're definitely presenting a proof to unlock the coins in the first place, but you might then  put them under a certain kind of computer program, a certain kind of locking script that  looks at something beyond just a signature to unlock.
Maybe it looks at the structure of the  transaction you're spending it into.
And so this is a very general, a very powerful idea.
And for a long time, I mean, maybe we can talk about this later.
I wanted to tell people we're  very worried about that idea enabling something like government control of coins, but that actually  turns out not to be any kind of a concern, really.
But basically, you can use this really powerful  new ability to do something like Volts, which just exactly what you said, is this idea, if someone,  let's say someone gets a hold of the key that you used to do this unvaulting process, right?
They start to try to move the coins, but because you've locked the coins into a vault with a delay  period, they have to wait, say a day or a week or maybe even a month to move the coins.
And then  in the meantime, you have some very trivial, you know, system or program that's monitoring the chain  and sees, oh, wow, I just saw an attempt to spend on your vault.
Did you expect that?
And if you  you didn't expect that, you can jump in and immediately sweep those funds into a recovery path.
And so the idea is that, I mean, this, if you get the tooling right, like this makes Bitcoin theft  exceptionally difficult, because what it allows you to do, and let me know if I'm jumping the gun  here, but it allows you to generate this recu- the keys to this recovery path in a completely  different way, and perhaps a very sort of impractical or operationally difficult way, then you're sort  of everyday keys, right?
So you could do a completely offline key generation, like you can generate  the keys in such a way that they would be almost like useless for use in a multi-state  quorum, which is what people do now to secure their coins.
They have, you know, maybe a multi-state  quorum with a few different kinds of keys or devices, and that's great.
But if you're talking  about like super, super, super cold storage, you know, you just kind of can't use that in a  everyday, in a multi-state quorum, just kind of coin.
So, but with vault, your recovery path could  be that like ultra-cold path.
And so I think, you know, between that and sort of the, the ability  to intervene, if someone does capture your, you know, unvault keys, which definitely could be  multi-sig or could be really any kind of Bitcoin, a key arrangement.
You know, that it's a very  powerful combination.
Gotcha.
Yeah.
And so can you just explain for listeners, who are the typical  users here?
Like are we thinking of like big institutions?
Are we thinking of, let's say, a family  office with a lot of coins?
Or are we talking even like DIY, toddler average stack of guy is going to  use this kind of setup?
Or is it even like to the level that you might have like a mobile phone,  Bitcoin wallet with a vault kind of setup?
Could you just explain who do you see as the primary  users here?
Very, yeah.
So, when I started thinking about this stuff, I was really kind of a  moron personally with my own coins.
I had, you know, a single-sig with a passphrase, basically.
Yeah, it's a reasonable setup to docs myself.
I mean, yeah, it's pretty low tech, right?
But I was, like I said, I was sort of in an industrial custody context, or at least was exposed  one.
And I was really, really trying to think about how to de-risk those operations.
And, you know,  vaults were known at the time, but the problem was with the existing vaulting strategies,  were that like, they're just operationally extremely difficult.
And we can talk about that in a  little bit.
But what I really love about this proposal is that it kind of hits the full spectrum.
I  think, you know, everybody from kind of the biggest custody operations to, you know, individual  toddlers have the, you know, it's very easy to use this new construct, upfall.
Like the user  interface, if you will, is like very, very simple, but flexible enough to sort of accommodate  any use case.
And that's in large part due to, you know, the power of covenants.
I see.
Yeah.
Okay.
So, um, your paper also mentioned, so talking about covenants as well,  your paper mentions to kind.
So it'd be cool if you could explain that.
So we have the precomputed  and general.
So could you just explain what, what are those?
Yeah, sure.
So, um, again, the idea of a  covenant is that you are encumbering coins, not just on, you know, the initial unlocking script.
But,  um, you're actually encumbering them on the basis of the transaction that the coins are going into.
And so what that means is you have two options here.
You can either do something where you basically  pre compute like a tree, all possible paths of, you know, how these coins can flow through this,  this vault thing over the lifetime of, you know, some number of transactions.
Or you could encode  a more general program almost in the script that is not bounded to a particular number of transactions.
And the second is significantly more powerful, obviously, because you could, for example, have a vault  where, you know, you can, you know, partially on vault as many times as you want,  revolt and so forth.
But the difficulty there is that up until now, all of the techniques for doing  this, this general covenant thing, um, were sort of complicated and scary.
And well, maybe the,  the techniques themselves were not complicated, but they resulted in these scripts that were  really, really complicated.
So an end user to use one of these general covenant techniques would  have to write like a very, very long, or relatively long, and complicated Bitcoin script.
I mean,  it's like, if people out there are familiar with like the difference between assembly language  and, you know, say Python, um, you know, if you're, if you're writing Bitcoin scripts to do  something like what, uh, vault does, you're essentially writing like assembly language versus,  you know, calling some Python function.
Um, but, um, these, these precomputed faults are still very  useful.
And I think, um, specifically in the case of like, um, a proposal called check template  verify that Jeremy Rubin and others, um, have worked on, um, that's, that's still a very useful  construct for a variety of things.
And the idea there again is you're sort of saying, okay,  I'm going to lock up these coins into a predetermined flow of transactions, but I know  that at some point that flow of transactions will, will terminate and I'll just kind of get regular  coins out.
Um, but the problem with that is, uh, is that, you know, you've got to pre anticipate  all the different ways that you want to spend.
And so if you're talking about, um, you know,  vaults, uh, that, that introduces certain limitations.
Yeah, gotcha.
And your paper also calls out  this idea that, as an example, there's this issue, similarly with lightning of understanding  what's the fee right now when we start the vault and then let's say in five years time when we  unfold, the fee rates could be totally different.
And I understand in lightning, they have this  concept of an anchor output.
And I know, uh, from the paper, you also mentioned a similar kind of  idea of, um, anchor, sorry, what was the terminology?
If femoral anchors.
Yes, femoral anchors.
Um,  so could you tell us a little bit about how, um, the, the goals, I guess are like, what,  what is a good vault, uh, proposal going to look like?
Yeah, so, um, I think there are certain  features that a vault should have.
So I, I guess maybe by way of comparison, um,  do you think it's worth talking through how, uh, you know, sort of the most basic vault  implementation with pre-sign transactions work?
And kind of show, let's, let's talk about that  and then kind of look at what's, what's the difference with up vault?
Yeah, yeah, because I think  it's hard in the abstract if I start describing, you know, features of, of vault, you know,  they're kind of like, uh, abstract.
And so I don't, I don't think they make sense until you kind of  of see the alternative.
Um, but right now, if you want to do one of these vaults with Bitcoin,  what you would do is you would generate this like one time key, uh, that you intend on throwing away.
Um, and you would send your coins into some transactions, uh, that are controlled by this one time  key.
And then you would use that key to sign a few sort of preformulated transactions that,  essentially lock the spend paths into these transactions that you've generated.
Does that make  sense?
Yeah.
Gotcha.
So it's kind of like very, um, it's a very critical setup step.
And then you  also want to make sure that key never gets compromised because, yeah, you know, if that key gets  compromised, yeah, you know, as a user, if you do this setup ceremony, like you better hope that  the key was actually deleted because then someone has the ability to spend these funds that you  think you've vaulted, but, um, you know, you actually didn't.
Um, and in fact, key deletion, like  is notoriously sort of impossible to prove.
And this is especially a concern in an industrial  context where, you know, you might have to prove to auditors that you're, um, that you're doing  everything right.
So, so for both individuals and, and companies, it's, it's pretty tough.
Um,  so that the setups ceremonies can be fairly onerous for something like this.
And then  along the lines of what you were mentioning a few minutes ago about fees, you know, because you're  pre generating these transactions, you're locking yourself into some set of fee rates, you're  locking yourself into, uh, the set of destinations that the funds can be involved to and, you know,  that might mean that you have to use some kind of intermediate hot, hot-ish wallet to actually route  up the funds after you've unfolded them.
Um, and so, um, you know, there's still value, perhaps,  in doing this kind of a setup, because again, it gives you that delay period where you can  contest, you know, hacker trying to spend your coins, but, but there are all these operational  considerations and, um, you know, it makes it, you have to think about a whole lot upfront, do  everything right operationally.
And then kind of hope that you've chosen the right, you know, say  fee rates to pre generate.
Um, so if you, if we think about, and this is really how the development  of this started out for me was, um, sitting down, I didn't intend on writing a software proposal  to be honest with you.
I, I almost wanted to come up with a thought experiment about what the perfect  vault would be.
Um, and so for one, I think for the perfect vault, um, you can have multiple deposits  to the same vault, uh, with, with this pre signed approach, you basically create the vault that  you're going to create.
And then that amount is sort of fixed until you just like a one time deposit  rather than multiple deposits.
Let's say, yeah, exactly.
Um, whereas I thought, you know, you should  be able to choose these vault parameters and then just kind of deposit so that, for example, if,  if you're, if you want a DCA on an exchange, say, every day, um, and you want to have that  withdrawal go immediately into your vault, you should be able to do that without any kind of  operational headache.
Um, so that's one.
Um, another is this idea of having a dynamic vault target,  or I'm sorry, dynamic, unvault target.
And what that means is when you want to go to withdrawal  from your vault, instead of having to lock in some fixed intermediate wallet that you're with  rolling to and, you know, hoping that that doesn't get compromised, um, because of, you know, if that  does, then you've got to sweep to your recovery path, which is probably a big pain to actually go  in access.
Um, if you could actually just pick where you wanted to withdraw to, um, and then start  the unvault process with those parameters.
So this, um, dynamic unvault target allows you to do that.
Then the other thing, um, that you want, that's, that's probably just nice to have, but, um,  this idea of doing partial unvault where you're not moving the entire balance of everything that's  faulted at once.
You're just kind of peeling off some amount, um, to unvault at a time.
Gotcha.
Right.
So you could have like a big saving amount.
And okay, that Bitcoin has gone up so much.
I'm going  to peel a small amount off and buy a house for the family, but keep the rest in the vault.
That kind  exactly.
Yeah.
Kind of use case.
Let's say.
Yeah, exactly.
And then the final thing that you want,  which is kind of an implication of the dynamic targets, um, is this idea of batching?
Um, batching is, is really, really important because if you're generating all these vault outputs,  um, then you don't want to have to, you know, generate,  unvault outputs for every single vault that you, um, that you create.
Because otherwise,  let's say that an attacker gets hold of your hot wallet keys or your unvault keys.
Um,  then, you know, they might start to withdraw, um, you know, could be thousands and thousands of  vaults, depending, depending on your scale of custody.
Uh, and so in a case like that, you want to be  able to sweep to the recovery path, um, as efficiently as you possibly can in batch.
Um, and so that's  one of the big innovations of up-vault is that, um, it's the only proposal to date that actually  enables that.
Yeah.
So to be clear, in this case, this is more useful for, let's say, a professional  large scale custodian who is perhaps managing thousands of vaults and maybe not as useful for,  let's say, the individual hard luck just doing one vault for himself, right?
Is that,  I don't understand.
Well, that's, that's an interesting question because if you want to allow people  to, let's say with, you know, deposit to these vaults on a daily basis, the only way that you can  actually have multiple deposits like that work is with separate utxos.
And so at the end of the day,  um, you know, you've got to spend this utxos.
And if you don't have batching, then that becomes  a very inefficient process with a vault.
Uh, so naively, yeah, it does, it does look like this is,  you know, only a big deal for big custodians, but it's really not.
It's, it's a big deal for any  user of all, I think.
Um, and so this idea of batching, I think without it, it's very hard to make  vaults a practical thing.
Gotcha.
And just out of curiosity, even today, there are limits on how  many utxos you can have in one transaction, right?
I don't know the exact number.
Someone correct  me, but it might be like a hundred or maybe more, maybe a little bit more.
Um, so let's say this  stack has been stacking, you know, once a day for years, he might have like 800 outputs or something,  right?
And so even that would have to be, um, let's say broken down into chunks that are actually  doable.
Absolutely.
Yeah.
Absolutely.
I mean, you're, you're still sort of hitting the same problem,  you know, if you've got, uh, we'll say you're doing your daily DCA.
True.
True.
Yeah.
To be fair to you, that's, that's a problem already today.
So, you know, you could be really screwing  yourself over if you're not careful about how you manage your coins today.
So we're not going to like  ding you for that or anything.
Um, but, uh, yeah, uh, that makes sense.
So let's talk a little bit  about the relation of this with some of the other ideas that people have been talking about.
So  as you mentioned, and I've, I've got an episode with, uh, Jeremy Rubin talking about CTV, uh,  probably a year or two ago now.
Um, and they're at the same time that the CTV drama happened.
I  think there was also, there were other proposals, right?
I think Rusty from Blockstream had another  idea.
I think it was OptiX hash.
And then some other people were talking about a combination of,  I think it was check seek from stack and cat, um, which could do something as well.
So could you  just talk a little bit about the relation with vault, up vault as opposed to some of the other ideas?
Sure.
Yeah.
So, um, I think a lot of people have realized that bringing covenants into Bitcoin somehow  is a really, really, really good idea.
Um, perhaps even essential if you think about the need for things  like, um, coin pools, um, to actually scale it, you see ownership.
It certainly vaults, I think, is  increasingly seeming to me to be an essential thing for custody.
Um, uh, but yeah, this problem of  how to actually bring covenants into Bitcoin in the right way, uh, is very, very thorny because  not only do you have the option of doing say precomputed covenants, which are sort of simpler, um,  versus these general covenants, but then even within those two categories, you've got a whole  number of different options for, for actually implementing this stuff.
And so the design space,  there is wide open.
Um, and there are a lot of different proposals, each of which has certain  limitations and certain advantages.
Um, you know, check template verify, for example, uh, is,  is very, very simple.
And I've reviewed it in depth.
And I think it's a safe change for Bitcoin,  but it does have certain limitations, mostly in that you have to actually, you know,  precompute this, uh, graph of transaction.
So anyway, to step back, like solving the general  covenants problem is kind of like a holy grail at this point.
And it's really, really difficult.
Um,  vaults in particular are just a use case of covenants.
They're kind of like, um, a subset of the,  the covenant functionality.
And so, um, one of my ideas here was instead of trying to solve the  general covenants problem, which a bunch of people have done and is kind of a quagmire at this point,  I figured I just want to do as good a job as I can on vaults.
And, you know, maybe that requires  some covenant like behavior, which, which it turns out it does.
I say so maybe it can be interpreted  as you're trying to thread the needle here in terms of trying to solve this grand grand problem of  trying to do the whole covenant shebang, uh, but trying to give people the specific thing that's  needed for people to be able to vault and unvolt their coins.
Is that a fair summary?
You would say,  yeah, yeah, yeah, absolutely exactly.
Okay.
And so I spent, um, you know, I was excited when I finally  understood check template verify and, um, you know, work with Jeremy a bit, um, and actually  developed a prototype of implementing vaults within CTV.
Um, in the advantage that you get there is that  you don't have to do this really, um, precarious ephemeral key thing where you generate the one  time key and then throw it away.
Um, CTV just kind of enforces the, the, the covenant on chain, um,  which is great, but you still have the problem of dealing with fees because with CTV, because you're  precomputing the exact, uh, you know, flow of transactions and then committing to it in a hash,  kind of like mercultries if people are familiar with that.
Um, you have to pre specify, you know,  the withdrawal paths, the recovery paths, the, um, well, I guess you have to specify the recovery  paths in any case, but, um, the, uh, the fee rates, um, and so it's like it's an improvement for sure  over the pre sign transaction implementation of all, but it's still left me kind of wanting in  terms of functionality.
I see.
So yeah, so basically you see it like vault offers a different  functionality to what CTV was.
It's, but it's not the full covenant thing.
So exactly.
Yeah.
Okay.
Yeah.
Um, and gone.
Oh, go ahead.
I'm gonna say that, uh, CTV CTV is much more general than  up vault, but up vault has some behavior in there that CTV can't do.
So it's, it's not like one  is a subset of the other other.
Gotcha.
Yeah.
Yeah.
That's yeah, totally fair.
Um, and so could you  tell us a little bit about just the life cycle of this process then?
So like, let's say we had up vault,  what does it look like to start a vault, you know, transact, uh, or even do, let's say a partial  unvolting and then at the end, you're closing down the vault because you're passing it on or  inheritance scenario or something like that.
If you could just talk to a life cycle there.
Sure.
Yeah.
So when you're creating a vault, um, all that means is that you're, um, unlocking some  coins that you have control of or getting someone to send you some coins.
Um, to what's called a  script pub key in the script pub key is is basically the name for that puzzle that you have to solve  whenever you spend a coin.
Um, and the contents of that script pub key contain, um, an opcode,  op vault, say, um, that has, uh, three parameters.
Um, the first parameter locks you into a certain  recovery path.
So that determines, you know, what your super cold key is going to be.
The second  parameter is the spend delay, which is just a number.
It's, it works exactly in the way that, um,  check block time verifying check.
I'm sorry, check sequence verify works, um, in that you can  specify relative delay, um, in terms of either time or blocks.
And then the third parameter that you  give it is, um, uh, the unvault key.
And so that's basically like what, what's the mechanism that  I'm going to use to authorize the start of the unvault process.
Um, so once you have that script,  you can just, you know, send you txos to be encumbered by that script kind of as much as you want.
Um,  and at any time, you can sweep those vaults into the recovery path with no delay whatsoever.
Um, yeah.
But if you kind of like a sort of like a, it's sort of like a watch, you sort of need  some kind of watch tower like feature kind of like lightning this idea of a watch tower, but you're  watching to see, oh, somebody spending my coin.
Oh, quick.
I need to use my recovery key to kind of,  you know, but, but I know I'm safe as long as I have the watch tower that detects it within a certain  time period, right?
Depending on how many blocks we set that, that time lock, right?
Um,  and so then as I understand, then the idea is, you know, let's say I put some coins into my vault.
I see, oh, look, someone's stealing from me.
Okay.
Let me recover those coins into my recovery pathway.
Uh, because that other hack, the hacker guy is hazing covered by the time lock, but I am not.
I can just pull  it straight out to my recovery.
Is that the same?
That's the setup.
Yeah.
Yeah.
That's exactly right.
Um, so, so yeah, when you, if you want to start the unvault process, then you send  some amount of the vault into the script, you know, that's, that's up unvault with the exact same  parameters, except instead of specifying the unvault key, you're specifying the target hash,  which basically locks you into what is, where is this withdrawal proposing to go?
Um, and just  as you said, what you want when you're using vaults is some kind of a watch tower.
Um, and what's  nice about the watch tower for vaults is that it's, it's exceptionally simple.
Um, and you can do  it in a variety of ways under a different, you know, a variety of trust models.
So for example,  let's say that I don't want to run this, this watch tower myself, but maybe I'm comfortable with  like the watch tower company knowing which outputs, um, you know, I have, you can tell them what  the outputs are to watch.
And then they can alert you if those start to move and then you can  make the judgment call whether they're interviewed or not.
Or maybe I want to give them, you know,  my recovery pathway and then they can just scan, you know, for any, any movements associated with  that recovery pathway.
And that can give them the recovery transactions and then they can broadcast.
That's a, that's putting more trust in the watch tower.
Or maybe I don't trust the watch tower at  all.
And I can give them some kind of probabilistic data structure that might tell me if my coins  are moved or, you know, maybe like kind of like a bloom filter, they might give me some false  positives for whether the coins are moving.
But the watch tower can sit there and then I can,  you know, get an alert from them about maybe, maybe your coins are moving and then, um,  jump in and check myself.
So the point being, um, that there are a variety of ways to,  to run these watch towers and they're, they're very, very simple things.
Yeah.
And so one  of the question with the recovery pathway.
So is it the case that let's say you are a big custodian  and you are managing thousands of vault, the thousands of customers, when you have to do the recovery  or to kind of, you say that there's a hack, does that mean you would need to now pull all,  all of them at once?
Or can you individually, you get what I'm asking?
Yeah, absolutely.
So, um,  it depends on whether the vaults share a recovery path.
Um, and in practice, I think what you would do  typically is you would say, okay, I have my ultra cold, um, key.
I'm going to take the expub of that key  and then just generate different recovery paths as needed so that they're all locked by the same,  you know, super cold key, but you're getting different recovery paths so that, um, because  exactly as you're saying what happens is when you sweep one vault with a given recovery key,  because there's no additional authentication required, or authorization required to actually  do that sweep, um, anybody might be able to come along and just kind of replay that sweep  against vaults that share that recovery path.
Now, um, one proposed change that I'm kind of noodling  on after putting the initial release of this out there, getting some feedback from the other  is one option is you could actually, um, give some flexibility around how the recovery path works.
So right now, I just say, okay, if, if, if the coins are headed into the recovery path, just  that, you know, it's valid.
Let's do it.
Um, another option would be you could do that, or you  could decide to say, you know what?
Actually, this recovery path is protected by another key  that I have to sign with.
And so you don't have that replayability problem.
Um, so that,  that option would introduce a little bit of, um, flexibility, but then, you know, it makes it a little  bit more complicated to decide for a vault user what they should do.
I see.
Yeah.
Okay.
Um, so  with the unvault process, like the normal unvault process, that still allows you to specify a  different address, let's say, like a new address to receive the vaulted coins out into.
Um,  but it's just the recovery path has like specified, uh, pathways, does it?
Yeah, exactly.
Um, and the  idea there is that, you know, when you set up the vault, you want to say this is the only way to  recover these coins, um, because that's a special ability to be able to sweep all of the value into,  one path.
So yeah, the recovery path is, is, is pre specified and completely static, but the  recovery path could be like, say, a taproot script where you have a whole, you know, you could do  something where you say, okay, my recovery path is that, um, within six months, I can spend it,  or I can spend it immediately with my super, super cold keys, or after six months, um, you know,  I can spend it with this, like, backup set of keys.
So you, you can do anything that  taproot allows you to do with the recovery path, which is, you know, a huge range of flexibility.
I say, right.
So because of that taproot ID with like the public case band or the script path  spend, you can set up a different, you can set up different scenarios and, you know, people  talking about this idea of having, let's say, like a degrading set up, right?
Like that author  of set in amount of time that only took out of whatever five keys or whatever, um, keys could spend,  um, one other question I had as well is there's this idea in your paper, it's saying, uh,  being able to sweep to the recovery key at any point with no witness data, does this just push  the problem back one step?
Like could their criminal or the hacker just try to find out the recovery  key or like hack that part?
Is that just pushing the problem back one step?
It, um, I would push back a little bit because, um, so they have to figure out two things.
Well, I mean, if they compromise your sort of backup recovery key, uh, then yeah, totally.
I mean,  that, you know, they can generate the data necessary to sweep all the vaults and everything.
I think the idea here is that, um, we all know at least in theory how to generate a really,  really, really cold key.
It's just that oftentimes we don't do that because it's, it's very  inconvenient and, you know, basically inaccessible.
Um, but, uh, but, but yeah, I mean, if someone  finds your, just in the same way that if, if someone right now kind of discovers your, uh, uh,  your, your, your, your keys, you know, your hose, um, the idea here is that this just allows you  to kind of like segment that process from sort of the everyday operation of spending coins.
Um,  and it gives you some granularity and insecurity if that makes sense.
But, but push me on that  if it doesn't make sense.
Yeah.
Yeah.
No, I think I'm getting you there.
So I think the way I'm  seeing it then is it's sort of like you could have this separate set up with much harder to access  keys than what you're, you're, you're normally using.
But I guess today, today nowadays, let's say  if you, if you, if you're like a serious hot load with lots of coins or maybe you're a company,  you might have today a hot wallet with a small portion of your coins and I called wallet with  like some, you know, big, big multi seagout, just keys, distributed and all this kind of complicated  stuff.
So I guess that's kind of what people are doing today, but in fairness, not everybody can  use multi seag today.
Now of course there's my sponsor, Anjain Kaprul and there's, you know,  the inspector and Sparrow and all this stuff out there, but I think in practice, and I think that's  where your proposal is getting at is like this idea that it could give the benefits of multi seag  for people who currently do not have the, either technical means or the comfort to use multi seag today.
And I, that's where I'm seeing it at least.
And then I mean, you know, in an industrial context,  like multi seag can be very troublesome, getting together, you know, enough of a signing  forum, you know, that means managing, you know, a diversity of teams and devices and it's just,  it's really a lot of kind of like amortized overhead for the operation of coins, whereas with this,  you know, you can have, you can have sort of a streamlined setup for spending.
And then if something  goes wrong with that setup, you can just fall back to like a really, really secure system, but,  but kind of on a day to day basis, you can have something that's, it's really secure, you know,  whether that's kind of a lighter multi seag or some kind of, you know, from your secret sharing or  MPC thing.
But it's just easier to use than like like having a single multi seag configuration  that's both extremely robust, but also kind of permits spending.
So it makes sense to me that  you want to segment kind of the security model a little bit for those two.
Okay.
Yeah.
Can you also explain the reliance on package relay?
Because that's something also mentioned in  in your paper.
So just pack, if you could just give like the super high level of what package  relay is and then explain the reliance there.
Yeah, sure.
So package relay is the pretty simple idea that  if you have a number of unconfirmed transactions that depend on one another, you should be able to  relay those to the peer to peer network.
And they should be able to travel together and have  a kind of aggregate fee rate that allows nodes to say, okay, well, this parent transaction has a  really crappy fee rate, but the child transaction pays a ton.
So it together, if I mine them together,  I actually get a very attractive fee rate.
And this is important because like pretty much any  second layer contract application for Bitcoin involves sort of pre specifying a fee rate, at least,  you know, so in lightning, for example, what they do is, you know, the commitment transaction has  some fee rate itself, but then to support dynamic fee adjustment during settlement time,  there's an output that anybody can spend that they call the anchor output.
And  this allows you to do child pays for parent.
But things kind of get into trouble.
If you don't  have package relay, because maybe the parent is so low fee that it can't even broadcast to land  in the mump pool to get bumped by the child.
So anyway, package relay is very, very important.
And  pretty much everybody wants it.
Gloria and others are working on a proposal there and it's looking  like it's going to come along pretty shortly.
But the one one and the sort of it is that  package relay just allows us to do dynamic fee adjustment in a way that, you know, let's us kind of  not worry about potentially getting typhooned by other than in pool fees.
Yeah.
Yeah.
And for an, listen, it's interested.
I have an episode with Gloria talking about  package relay, of course.
And one other question I've got is there's a bit more chatter about  manuscript right now.
So I'm curious, does mini script play into this at all?
Does it help?
Does it not  help?
You know, I, I'd say it's sort of unrelated.
Like if up vault, why don't up me heat in,  there would be a mini script.
I don't know what they call them function for for up vault and not  involved.
But what's nice about hop vault is that like the outcomes are very, very simple.
And  this, the resulting scripts are very, very simple.
So typically mini script is a big benefit.
If  you've got, you know, some kind of relatively complicated, I mean, using multi-sig and Bitcoin  script is, is cumbersome to say at least.
And so something like mini script, there, if you're,  you know, if you're composing things of time locks and multi-sigs and making very complicated  scripts for mini scripts is a huge win.
I think it's still be great, you know, for up vault,  but it's the mini script and the Bitcoin script for up vault look very, very similar.
Gotcha.
Gotcha.
Yeah.
And with these, it's like, it's, it helps, but it's not a huge win.
Okay.
And then actually one other question I had was around one of the, I guess critiques, let's say,  of the general covenant schemes, because I think in your paper, you also mentioned that,  that it wouldn't be suitable because they would result in very bloated script pub keys.
So could  you just explain that a bit?
Yeah.
So again, you know, general covenants give you this very low level  machinery to essentially write, you know, computer programs in script that determine the  spin path of the, the coins.
And because you're articulating something like a vault in Bitcoin  script, to get, to get the equivalent functionality of what something like up vault provides you,  you have to write like really long, really complicated script.
And a lot of people have proposed  these general covenant mechanisms, but I haven't seen a lot of actual end uses of them, because I  think the resulting scripts are just so gnarly that they make the proposals kind of un-attractive,  at least for me personally.
And then the other problem is, you know, let's say that you have one  of these general covenant mechanisms.
And someone devises, you know, they go to the time and write  this giant script that does everything that you want.
And everybody's, you know, wants to use it.
Well, now you've got everybody kind of doing the same thing, but they're bloating the chain space  with the same exact script, you know, that's really, that's really big.
So I think kind of the  bold case for general covenant stuff is that it allows end user experimentation.
And you don't have  you know, get a software done if you want some new big piece of script functionality.
But I think in  actuality, if you had something like that and some exciting use comes along that's relatively  complicated, you'd really have to software condense at some point because the waste would just be  so much in terms of the witness sizes.
Go ahead, sure.
Okay.
And so one other question, is there anything  specifically enabled by Taproot here or not?
Not really.
This could have as easily been done with  bear script or pay the witness script hash.
And indeed, the way that this written right now is it's  kind of compatible with anything.
It's not Taproot only.
So I mean, Taproot certainly helps,  but it's not, I wouldn't say the two are directly related.
Yeah, sure.
I saw from the mailing list,  there was some interesting discussion.
I think Greg Sanders had this suggestion and you were  commenting that this could allow all the the outputs to be paid to Taproot.
So that could be maybe  some small part privacy benefit there.
Yeah, I think so.
I'm trying to think through that one  because so originally when I wrote this, you could do the out vault output any way you wanted  so Taproot or segwit version zero.
But then when you went to spend it into the  up, on vault output to sort of trigger the start of the withdrawal process, that had to be a bear  script because, you know, when a script interpreter is looking at that up on vault output, it's  saying, okay, is this compatible with the up vault, it's spending?
And mostly due to my own  inexperience.
I was just like, okay, well, it needs to be bear so that we can read it directly.
But  when I put the design out there in the code, Greg Sanders came back and said, hey, if you just  stick this extra little bit of information in the witness when you're spending the out vault,  you can actually support doing the up on vault in any kind of address type.
And, or any kind of script hash address type.
So that was a big improvement.
I actually  implemented that and pushed the code last night.
I think that's a big upgrade.
Okay, fantastic.
And any other feedback you've received on the proposal so far?
No, it's all been pretty positive.
I think people were just kind of hungry to see like  a more narrow proposal, a more specific application of some of this covenant stuff.
I'm happy that I release the paper and an implementation at the same time because  I think a lot of people have been proposing ideas on the mailing list.
And, you know, it's  one thing to write an email, but it's another thing to actually like code it up with some tests  and see it working.
So, so feedback has been good.
I mean, I think the next step is probably to  write a bit.
And I'm pretty mellow in terms of activation.
I mean, look, I think, I'm sorry,  drop my headphones there.
I think, I think it'd be a huge benefit to have this in Bitcoin.
I  would use it personally.
I know, you know, a lot of industrial users would use it personally.
I  think it makes custody a lot safer for anybody.
But I'm not really, you know, my expectations about  what's going here very tempered because you just can't have expectations about that kind of thing.
Especially after watching the happen was Jeremy and right.
I think it's probably a case where  maybe the community hadn't been let's say brought on board with it.
And maybe that was,  I don't know, I'm speculating.
Right.
It seems that's what it seems like to me.
But that's it.
I mean,  if it helps Hodler's hodl in this case, you know, I think that there could be a case there,  like people could see, oh, you know what, this actually could be useful.
This could be handy for people.
So let's see what happens there.
Hey, yeah, right.
Right.
I know, yeah, with with Jeremy and CTV,  you know, it's it took me a long time to actually appreciate what CTV does because when you first see  it, I just think Jeremy's clock speed is like three acts of what everybody else is.
And you know,  like we all have our strengths and weaknesses.
I think Jeremy's brilliant.
But when I first came across CTV, I was like, you know, what the hell, what do I want this for?
And it took me a while to actually internalize what some of the uses there are.
I think  up vault is a little bit easier to approach because the again, the use cases just soap their cut.
And you know, keeping coin safe is kind of everybody's concern in Bitcoin.
And so it makes it a little  bit easier to evaluate kind of whether or not it defaults the right thing ultimately.
Yeah.
Yeah.
I think it it certainly seems more crafted with this particular use case in mind,  whereas I think if a proposal comes and it and it's like extremely general and very conceptual,  you kind of have to be really deep into the technicals or really, really into it to  go spend the time learning about it and then pushing for it because, yeah, for this kind of thing,  I think people it just seems like the bar has risen a lot for what would require, whereas if you  went back years and years ago, people they used to do self-forks pretty regularly.
But well,  I guess yeah, let me just see if there's anything else I'm just thinking.
You know, actually on that note, I mean, I just like to comment a little bit.
You said something interesting just now, which is, you know, we used to do self-forks  more regularly.
And you know, obviously like Bitcoin was more nascent and smaller back in the day,  but I mean, people forget like we we activated, you know, check sequence verice five, check  box time verify BIP 68 all within the same year.
And that was pretty close to segment.
And so I think, you know, more than anybody trust me, I get that there are certain things  about Bitcoin that we don't want to change.
I get that like this is the base layer and you  want to be very risk-averse, but Bitcoin definitely isn't finished.
And that's an easy kind of  tagline to use on Twitter, but there are certain aspects of Bitcoin that I think really do  need to change to facilitate the use that they're all kind of hoping for.
And so I think  I hope we can be less skittish about evaluating proposals kind of from first principles,  you know, determining like whether they're safe.
And then, you know, looking at proceeding  because, you know, as things stand, I do worry about Bitcoin stagnating a little bit.
And I think it's fair to point out as well that like you have to also consider what's the harm,  right?
Like so it let's say we do upvolt the other people being harmed potentially other people  who choose to use upvolt, correct?
Right?
It's not that upvolt has some kind of massive  negative externality on all the other hardlers and users of Bitcoin, right?
That's right.
I mean, you have to be diligent about  yeah, so the one exception to that would be if you could construct a pathological use of  upvolt that say makes validation very difficult.
And so, you know, you have to have a period for  a few months where people are just sitting there trying to construct these pathological uses  they can break.
You know, I sat there doing that with CTV for a while.
And I was like, well,  this thing kind of, I can't figure out how to break it.
And it's been months.
And a lot of people  who are favorable to it can't figure out how to break it.
So, you know, it looks safe to me.
And everything needs to go through that process because conceptually you're exactly right,  you know, if you introduce a future, maybe only the people using that feature are harmed.
But from an implementation standpoint, it could be that there's sort of contagion in terms of  validation.
I see.
Yeah.
So, yeah, at the end of the day, I think that was probably one other  critique that people were, I mean, just rewinding back to what happened with CTV.
I think people  were complaining that there was not any, let's say, commercial use cases of CTV or at least that  was one of the critical lines.
I'm not sure if that maybe you disagree with that, maybe there were.
But it seems that the idea of the vault, it seems a bit more very clear and very obvious  there are companies built around this whole idea of securing people's coins or helping them  secure their coins.
It seems like there is a bit more of a commercial use here.
And so there  for we might see more interest in this idea, at least that's my speculation.
Yeah, I think it's  it's a more tangible thing that more people can immediately go, oh yeah, I might have a use for that.
Or that will benefit me somehow.
I think with CTV, the irony is I think there were, there are a ton  use cases that might be really valuable like the DLC efficiency improvements.
This idea of  being able to initiate and receive lightning while you're, while you're completely offline,  or while you're signing keys are offline.
And then, you know, to an extent,  the vault there could be helpful.
But I think it was just tough when you think about trying to  understand and appreciate CTV because you were kind of blasted with all these like possible use cases.
But, you know, I think nobody, you know, a given use case wasn't maybe fleshed out or championed enough  for it to kind of go through.
And so it's all understandable.
I mean, I think  kind of from everybody's perspective in the CTV case, it's understandable.
I, you know,  I have all kinds of concerns about the Bitcoin development process.
And in, in, in no case,  you know, is it like, oh, somebody's doing a bad job here.
It's just kind of  the nature of trying to do something as decentralized and as kind of structuralistness,  as this whole process is.
Right.
And I think that was perhaps,  I don't know.
It's hard for me to, I'm not trying to put words in Jeremy's mouth, but it seemed that he  was perhaps unclear about what bar he had to meet to sort of get this over the line, maybe in his  mind.
And other people were saying, no, we just don't want to change it, don't change anything.
Like,  just leave it as it is.
And so maybe that's always going to be a debate and an argument going  when anyone wants to do any, literally anything with Bitcoin.
But perhaps it's about, if you,  if you get enough people on your side in terms of, let's say, if Bitcoin, the community,  whatever you want to call, is this anarchic mob of users, developers, miners, and companies.
And you sort of have to win enough of them over with this idea and say, look, there's so much value  here, we're going to, you know, make vault easier and that's going to make custody easier.
And  that may make people more comfortable to use Bitcoin, which obviously is going to grow our  network and grow the users and bring more people in.
Maybe that's the argument.
Maybe that's the  case you've got to make.
Yeah, yeah, that could be.
And I think we're in a little bit of  of tough spot because, you know, for the last major soft forks, there've been really a small set  of people extremely capable people who, you know, have proposed them and have written the code.
And  now some of those people have kind of stepped back a little bit because they rely on speculating  that maybe they realize that kind of having independence on, you know, the same group of people  making changes is not a healthy state for Bitcoin to be in.
And so, you know, as a result, this  process of making consensus changes is in a little bit of a, a no man's land where there's kind  of a vacuum in terms of like, okay, who do we, who's kind of the authoritative voice here?
And  of course, there shouldn't be an authoritative voice.
And so, yeah, you do like you're saying,  you do have to go out and get kind of this critical mass of community support.
And that's a tough  game because, you know, where do you cut the line on that?
So, so yeah, it's really, it's, it's  fascinating and, and very difficult.
Yeah.
Well, I guess, you know, I guess that's the question.
No, the final closing thought where to, where to, from here with up vault.
For me, I think, you know,  I've got a lot of irons in the fire with different projects I'm working on.
And so, I'm going to  probably write up a bit and then propose that.
And then I think I'll get the implementation  to a point where I feel pretty comfortable with it.
I'm sure I'll need, you know, a lot of  help from some of the gray beards and in terms of making sure the script interpreter changes are,  are really kind of ironclad.
But once I get the code into a shape I'm happy with and I get a bit  written, I'll just let it sit there, I guess.
And if people like it, you know, we can move forward,  whatever that means.
But otherwise, I'm just going to go back to my other projects and let it  hang out as an idea.
Fantastic.
Well, listen, I'll put the links in the show notes.
James's website  is JamesO.BE slash vault.pdf is where you can go to read it.
And there's a mailing list post and  a Twitter thread.
I'll put all the links in the show notes.
James, thank you for joining me today.
Hey, man, it's always a pleasure.
