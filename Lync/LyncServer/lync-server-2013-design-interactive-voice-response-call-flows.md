---
title: 'Lync Server 2013 : concevoir des flux d’appels de réponse vocale interactive'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Design interactive voice response call flows
ms:assetid: f3477f0a-3ad5-4b13-a73c-046aa451db19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413020(v=OCS.15)
ms:contentKeyID: 48185826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 428d1d40b32c8dfaec3b897549409016f2cb6984
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a><span data-ttu-id="26191-102">Concevoir des flux d’appels de réponse vocale interactive dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26191-102">Design interactive voice response call flows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26191-103">_**Dernière modification de la rubrique :** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="26191-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="26191-p101">Vous pouvez utiliser la réponse vocale interactive (IVR) pour obtenir des informations des appelants et acheminer l’appel jusqu’à la file d’attente appropriée. Les paires de questions et réponses déterminent la file d’attente à utiliser. Selon la réponse de l’appelant, celui-ci entend une question de suivi ou est acheminé vers la file d’attente appropriée. Les questions du système de réponse vocale interactive ainsi que les réponses de l’appelant sont fournies à l’agent qui prend l’appel, fournissant des informations précieuses à l’agent.</span><span class="sxs-lookup"><span data-stu-id="26191-p101">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue. Question-and-answer pairs determine which queue to use. Depending on the caller’s response, the caller either hears a follow-up question, or is routed to the appropriate queue. The IVR questions and the caller’s responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

<div>

## <a name="overview-of-ivr-features"></a><span data-ttu-id="26191-108">Vue d’ensemble des fonctionnalités du système de réponse vocale interactive</span><span class="sxs-lookup"><span data-stu-id="26191-108">Overview of IVR Features</span></span>

<span data-ttu-id="26191-109">L’application Response Group offre des fonctionnalités de reconnaissance vocale et de conversion de texte par synthèse vocale dans 26 langues.</span><span class="sxs-lookup"><span data-stu-id="26191-109">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="26191-110">Vous pouvez entrer les questions du système de réponse vocale interactive à l’aide de la conversion de texte par synthèse vocale, d’un fichier wave (.wav) ou d’un fichier audio Windows Media (.wma).</span><span class="sxs-lookup"><span data-stu-id="26191-110">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="26191-111">Les appelants peuvent répondre à l’aide de la voix ou de réponses de numérotation en fréquences vocales (DTMF).</span><span class="sxs-lookup"><span data-stu-id="26191-111">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="26191-p103">Les flux de travail interactifs prennent en charge jusqu’à deux niveaux de questions, chaque question et, selon la réponse de l’appelant, le système de réponse vocale interactive pose à l’appelant une question avec quatre réponses possibles, et selon la réponse de l’appelant, l’achemine vers une file d’attente ou lui pose une deuxième question. Quatre réponses sont également possibles pour la deuxième question. Selon la réponse à la question de second niveau, l’appelant est acheminé vers la file d’attente appropriée.</span><span class="sxs-lookup"><span data-stu-id="26191-p103">Interactive workflows support up to two levels of questions, with each question having up to four possible answers. The IVR asks the caller a question, and depending on the caller’s response, routes the caller to a queue or asks a second question. The second question can also have four possible answers. Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26191-116">Lorsque vous concevez des flux d’appels à l’aide de Lync Server Management Shell, vous pouvez définir tous les niveaux de questions de la série de serveurs et de toutes les réponses.</span><span class="sxs-lookup"><span data-stu-id="26191-116">When you design call flows by using Lync Server Management Shell, you can define any number levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="26191-117">Toutefois, pour faciliter l’utilisation par l’appelant, nous vous conseillons de vous limiter à trois niveaux de questions et cinq réponses par niveau.</span><span class="sxs-lookup"><span data-stu-id="26191-117">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="26191-118">En outre, si vous concevez un flux d’appels comportant plus de deux niveaux de questions avec plus de quatre réponses, vous ne pouvez pas modifier le flux d’appels à l’aide du panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26191-118">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Lync Server 2013 Control Panel.</span></span>



</div>

<span data-ttu-id="26191-119">Les questions du système de réponse vocale interactive ainsi que les réponses de l’appelant sont fournies à l’agent qui répond en acceptant l’appel.</span><span class="sxs-lookup"><span data-stu-id="26191-119">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call.</span></span>

</div>

<div>

## <a name="working-with-speech-technologies"></a><span data-ttu-id="26191-120">Utilisation des technologies vocales</span><span class="sxs-lookup"><span data-stu-id="26191-120">Working with Speech Technologies</span></span>

<span data-ttu-id="26191-121">Les technologies vocales, telles que la reconnaissance vocale et la conversion de texte par synthèse vocale, peuvent améliorer le produit et permettre aux gens d’accéder aux informations de façon plus naturelle et plus efficace.</span><span class="sxs-lookup"><span data-stu-id="26191-121">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively.</span></span> <span data-ttu-id="26191-122">Toutefois, il peut arriver que le texte spécifié ou la réponse vocale de l’utilisateur ne soit pas correctement reconnu par le moteur de synthèse vocale.</span><span class="sxs-lookup"><span data-stu-id="26191-122">However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine.</span></span> <span data-ttu-id="26191-123">Par exemple, le symbole\#« » est traduit par le moteur de synthèse vocale comme le mot «numéro ».</span><span class="sxs-lookup"><span data-stu-id="26191-123">For example, the "\#" symbol is translated by the text-to-speech engine as the word "number."</span></span> <span data-ttu-id="26191-124">Ce problème peut être atténué en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="26191-124">This issue can be mitigated by the following:</span></span>

  - <span data-ttu-id="26191-p106">Le moteur de synthèse vocale autorise cinq tentatives de réponse. Si la réponse de l’appelant est incorrecte (autrement dit, si elle ne figure pas parmi les réponses spécifiées) ou s’il ne fournit aucune réponse, l’appelant se voit offrir une autre opportunité de fournir la bonne réponse. L’appelant peut donner cinq réponses avant d’être déconnecté si aucune d’elles n’est correcte. Vous pouvez configurer le système de réponse vocale interactive pour qu’il lise un message personnalisé après chaque erreur de l’appelant. La question est répétée à chaque fois.</span><span class="sxs-lookup"><span data-stu-id="26191-p106">The speech engine gives the caller five attempts to answer the question. If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question. The caller has five attempts to answer the question before being disconnected. You can configure the IVR to play a customized message after each caller error. The question is repeated each time.</span></span>

  - <span data-ttu-id="26191-p107">Afin de minimiser le risque que le moteur de synthèse vocale n’interprète le bruit ambiant comme une réponse, utilisez des réponses plus longues. Par exemple, les réponses doivent comprendre plusieurs syllabes et être significativement différentes à l’oreille les unes des autres.</span><span class="sxs-lookup"><span data-stu-id="26191-p107">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses. For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

  - <span data-ttu-id="26191-p108">Si vos questions présentent à la fois des réponses vocales et DTMF, configurez les réponses vocales en utilisant des mots qui représentent le concept plutôt que la réponse DTMF. Par exemple, plutôt que d’utiliser « Appuyez ou dites un », utilisez « Appuyez sur 1 ou dites facturation ».</span><span class="sxs-lookup"><span data-stu-id="26191-p108">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response. For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

  - <span data-ttu-id="26191-134">Après avoir conçu votre système de réponse vocale interactive, appelez le flux de travail, écoutez les invites, répondez à chacune d’elles à l’aide de la voix et vérifiez que le système de réponse vocale interactive se présente et se comporte comme prévu.</span><span class="sxs-lookup"><span data-stu-id="26191-134">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected.</span></span> <span data-ttu-id="26191-135">Vous pouvez ensuite modifier le système de réponse vocale interactive afin de résoudre des problèmes liés à l’interprétation.</span><span class="sxs-lookup"><span data-stu-id="26191-135">You can then modify the IVR to fix any interpretation issues.</span></span> <span data-ttu-id="26191-136">À la suite de l’exemple précédent, si vous avez besoin \# de faire référence à la clé, vous pouvez réécrire votre invite d’un système pour qu' \# il utilise le nom de la clé, plutôt que le symbole.</span><span class="sxs-lookup"><span data-stu-id="26191-136">Following the previous example, if you need to refer to the \# key, you can rewrite your IVR prompt to use the key name, rather than the \# symbol.</span></span> <span data-ttu-id="26191-137">Par exemple, « Pour être mis en relation avec le service commercial, appuyez sur la touche dièse ».</span><span class="sxs-lookup"><span data-stu-id="26191-137">For example, "To talk to sales, press the pound key."</span></span>

</div>

<div>

## <a name="ivr-design-examples"></a><span data-ttu-id="26191-138">Exemples de conception IVR</span><span class="sxs-lookup"><span data-stu-id="26191-138">IVR Design Examples</span></span>

<span data-ttu-id="26191-139">Les sections suivantes contiennent des exemples de différents scénarios de réponse vocale interactive et de paires de questions-réponses.</span><span class="sxs-lookup"><span data-stu-id="26191-139">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

<div>

## <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="26191-140">Système de réponse vocale interactive avec un niveau de questions</span><span class="sxs-lookup"><span data-stu-id="26191-140">IVR with One Level of Questions</span></span>

<span data-ttu-id="26191-p110">L’exemple suivant illustre un système de réponse vocale interactive utilisant un niveau de questions. Il utilise la reconnaissance vocale pour détecter la réponse de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="26191-p110">The following example shows an IVR that uses one level of questions. It uses speech recognition to detect the caller’s response.</span></span>

<span data-ttu-id="26191-p111">**Question :** « Merci d’appeler le service des ressources humaines. Si vous souhaitez parler à une personne de l’équipe qui traite les salaires, dites salaire. Sinon, dites RH. »</span><span class="sxs-lookup"><span data-stu-id="26191-p111">**Question:** "Thank you for calling Human Resources. If you would like to speak to payroll, say payroll. Otherwise, say HR."</span></span>

  - <span data-ttu-id="26191-146">**L’option 1 est sélectionnée :** l’appelant est dirigé vers l’équipe en charge des salaires.</span><span class="sxs-lookup"><span data-stu-id="26191-146">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

  - <span data-ttu-id="26191-147">**L’option 2 est sélectionnée :** l’appelant est dirigé vers l’équipe des ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="26191-147">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="26191-148">L’illustration suivante montre le flux d’appels.</span><span class="sxs-lookup"><span data-stu-id="26191-148">The following figure shows the call flow.</span></span>

<span data-ttu-id="26191-149">**Flux d’appels pour un modèle interactif à un niveau**</span><span class="sxs-lookup"><span data-stu-id="26191-149">**One-level interactive call flow**</span></span>

<span data-ttu-id="26191-150">![Concevoir des flux d’appels à l’aide du réponse vocale interactive](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Concevoir des flux d’appels à l’aide du réponse vocale interactive")</span><span class="sxs-lookup"><span data-stu-id="26191-150">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="26191-151">Système de réponse vocale interactive avec deux niveaux de questions</span><span class="sxs-lookup"><span data-stu-id="26191-151">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="26191-p112">L’exemple suivant illustre un système de réponse vocale interactive utilisant deux niveaux de questions. Il permet aux appelants de répondre à l’aide de la voix ou de la numérotation en fréquences vocales (DTMF).</span><span class="sxs-lookup"><span data-stu-id="26191-p112">The following example shows an IVR that uses two levels of questions. It allows callers to respond using either speech or DTMF keypad input.</span></span>

<span data-ttu-id="26191-p113">**Question :** « Merci d’appeler le support technique informatique. Si vous rencontrez un problème d’accès réseau, appuyez sur 1 ou dites « réseau ». Si vous rencontrez un problème de logiciel, appuyez sur 2 ou dites « logiciel ». Si vous rencontrez un problème de matériel, appuyez 3 ou dites « matériel ». »</span><span class="sxs-lookup"><span data-stu-id="26191-p113">**Question:** "Thank you for calling the IT Help Desk. If you have a network access problem, press 1 or say network. If you have a software problem, press 2 or say software. If you have a hardware problem, press 3 or say hardware."</span></span>

  - <span data-ttu-id="26191-158">**L’option 1 est sélectionnée :**  l’appelant est dirigé vers l’équipe de gestion du réseau.</span><span class="sxs-lookup"><span data-stu-id="26191-158">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

  - <span data-ttu-id="26191-159">**L’option 2 est sélectionnée :** une question de suivi est posée à l’appelant :</span><span class="sxs-lookup"><span data-stu-id="26191-159">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="26191-p114">**Question :** « S’il s’agit d’un problème lié au système d’exploitation, appuyez sur 1 ou dites « système d’exploitation ». S’il s’agit d’un problème avec une application interne, appuyez sur 2 ou dites « application interne ». Sinon, appuyez sur 3 ou dites « autre ». »</span><span class="sxs-lookup"><span data-stu-id="26191-p114">**Question:** "If this is an operating system problem, press 1 or say operating system. If this is a problem with an internal application, press 2 or say internal application. Otherwise, press 3 or say other."</span></span>
    
      - <span data-ttu-id="26191-163">**L’option 1 est sélectionnée :** l’appelant est dirigé vers l’équipe de support des systèmes d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="26191-163">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>
    
      - <span data-ttu-id="26191-164">**L’option 2 est sélectionnée :** l’appelant est dirigé vers l’équipe de support des applications internes.</span><span class="sxs-lookup"><span data-stu-id="26191-164">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>
    
      - <span data-ttu-id="26191-165">**L’option 3 est sélectionnée :** l’appelant est dirigé vers l’équipe de support des logiciels.</span><span class="sxs-lookup"><span data-stu-id="26191-165">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

  - <span data-ttu-id="26191-166">**L’option 3 est sélectionnée :** une question de suivi est posée à l’appelant :</span><span class="sxs-lookup"><span data-stu-id="26191-166">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="26191-p115">**Question :** « S’il s’agit d’un problème d’imprimante, appuyez sur 1. Sinon, appuyez sur 2. »</span><span class="sxs-lookup"><span data-stu-id="26191-p115">**Question:** "If this is a printer problem press 1. Otherwise, press 2."</span></span>
    
      - <span data-ttu-id="26191-169">**L’option 1 est sélectionnée :** l’appelant est dirigé vers l’équipe de support des imprimantes.</span><span class="sxs-lookup"><span data-stu-id="26191-169">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>
    
      - <span data-ttu-id="26191-170">**L’option 2 est sélectionnée :** l’appelant est dirigé vers l’équipe de support du matériel.</span><span class="sxs-lookup"><span data-stu-id="26191-170">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="26191-171">L’illustration suivante montre le flux d’appels.</span><span class="sxs-lookup"><span data-stu-id="26191-171">The following figure shows the call flow.</span></span>

<span data-ttu-id="26191-172">**Flux d’appels pour un modèle interactif à deux niveaux**</span><span class="sxs-lookup"><span data-stu-id="26191-172">**Two-level interactive call flow**</span></span>

<span data-ttu-id="26191-173">![Concevoir des flux d’appels à l’aide du réponse vocale interactive](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Concevoir des flux d’appels à l’aide du réponse vocale interactive")</span><span class="sxs-lookup"><span data-stu-id="26191-173">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="26191-174">Meilleures pratiques</span><span class="sxs-lookup"><span data-stu-id="26191-174">Best Practices</span></span>

<span data-ttu-id="26191-175">La liste suivante décrit certaines meilleures pratiques lorsque vous concevez votre système de réponse vocale interactive :</span><span class="sxs-lookup"><span data-stu-id="26191-175">The following list describes some best practices for designing your IVR:</span></span>

  - <span data-ttu-id="26191-p116">Permettez à l’appelant d’accéder rapidement à la tâche. Évitez de mettre trop d’informations ou de longs messages marketing dans votre système de réponse vocale interactive.</span><span class="sxs-lookup"><span data-stu-id="26191-p116">Let the caller get to the task quickly. Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

  - <span data-ttu-id="26191-p117">Si vous souhaitez inclure un long message, envisagez de l’intégrer à la première question plutôt qu’au message d’accueil. Les appelant peuvent contourner le message s’il fait partie de la première question en répondant à la question, mais ils ne peuvent pas contourner le message d’accueil.</span><span class="sxs-lookup"><span data-stu-id="26191-p117">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message. Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

  - <span data-ttu-id="26191-p118">Parlez dans la langue de l’appelant. Évitez le langage emprunté. Parlez naturellement.</span><span class="sxs-lookup"><span data-stu-id="26191-p118">Speak in the caller’s language. Avoid stilted language. Speak naturally.</span></span>

  - <span data-ttu-id="26191-p119">Écrivez des invites efficaces. Supprimez toutes les options inutiles. Structurez les informations afin que la réponse attendue de l’appelant soit à la fin de la phrase. Par exemple, « Pour parler à l’équipe commerciale, appuyez sur 1 ».</span><span class="sxs-lookup"><span data-stu-id="26191-p119">Write efficient and effective prompts. Remove any unnecessary options. Structure the information so that the caller’s expected response is at the end of the sentence. For example, “To speak to the sales team, press 1."</span></span>

  - <span data-ttu-id="26191-p120">Rendez les réponses vocales conviviales pour l’appelant. Par exemple, si vous spécifiez des réponses vocales et DTMF, utilisez quelque chose comme : « Pour parler à l’équipe commerciale, appuyez sur 1 ou dites commercial. »</span><span class="sxs-lookup"><span data-stu-id="26191-p120">Make voice responses user friendly. For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

  - <span data-ttu-id="26191-189">Testez le système de réponse vocale interactive sur un groupe d’utilisateurs avant de le déployer dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="26191-189">Test the IVR on a group of users before you deploy it across your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

