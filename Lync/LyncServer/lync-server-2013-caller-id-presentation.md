---
title: 'Lync Server 2013 : présentation de l’ID de l’appelant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Caller ID presentation
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48184425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6962035f5de6b1b3885db3ff31b23058a71bdc4e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="caller-id-presentation-in-lync-server-2013"></a><span data-ttu-id="0e051-102">Présentation de l’ID de l’appelant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e051-102">Caller ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e051-103">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="0e051-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="0e051-104">Avec Lync Server 2010, le numéro de téléphone de la partie appelée (c’est-à-dire, le numéro de téléphone appelé) peut être converti à partir du format E. 164 vers le format de numérotation local requis par l’homologue de jonction (c’est-à-dire, la passerelle associée, le PBX (Private Branch Exchange) ou la jonction SIP).</span><span class="sxs-lookup"><span data-stu-id="0e051-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="0e051-105">Pour ce faire, vous devez définir une ou plusieurs règles de traduction pour traduire l’URI de demande avant de l’acheminer vers l’homologue de jonction.</span><span class="sxs-lookup"><span data-stu-id="0e051-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="0e051-106">Lync Server 2013 offre la possibilité de traduire également le numéro de téléphone de l’appelant (c’est-à-dire, le numéro de téléphone à partir duquel l’appelant est appelé) du format E. 164 au format de numérotation local requis par l’homologue de jonction.</span><span class="sxs-lookup"><span data-stu-id="0e051-106">Lync Server 2013 introduces the option to also translate the calling party’s phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="0e051-107">Par exemple, vous pouvez écrire une règle de traduction pour supprimer +44 au début d’une chaîne de numérotation et utiliser 0144 à la place.</span><span class="sxs-lookup"><span data-stu-id="0e051-107">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="0e051-108">**Pour configurer l’ID de l’appelant à l’aide du panneau de configuration Lync Server**</span><span class="sxs-lookup"><span data-stu-id="0e051-108">**To configure Caller ID by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="0e051-109">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0e051-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="0e051-110">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="0e051-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="0e051-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0e051-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0e051-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0e051-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0e051-113">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.</span><span class="sxs-lookup"><span data-stu-id="0e051-113">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="0e051-114">Dans la page **Configuration de la jonction**, double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.</span><span class="sxs-lookup"><span data-stu-id="0e051-114">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

5.  <span data-ttu-id="0e051-115">Pour configurer la présentation de l’identification de l’appelant :</span><span class="sxs-lookup"><span data-stu-id="0e051-115">To configure caller ID presentation:</span></span>
    
      - <span data-ttu-id="0e051-116">Pour choisir une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="0e051-116">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="0e051-117">Dans **Règles de traduction du numéro d’appel**, cliquez sur les règles que vous voulez associer à la jonction, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e051-117">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="0e051-118">Pour définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="0e051-118">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="0e051-119">Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0e051-119">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="0e051-120">Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="0e051-120">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="0e051-121">Pour plus d’informations, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0e051-121">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="0e051-122">Pour copier une règle de traduction existante qui servira de point de départ à la définition d’une nouvelle règle, cliquez sur son nom, sur **Copier**, puis sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="0e051-122">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="0e051-123">Pour plus d’informations, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="0e051-123">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="0e051-124">Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="0e051-124">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="0e051-125">N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit.</span><span class="sxs-lookup"><span data-stu-id="0e051-125">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

