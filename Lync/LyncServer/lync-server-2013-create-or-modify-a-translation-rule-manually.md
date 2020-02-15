---
title: 'Lync Server 2013 : création ou modification manuelle d’une règle de traduction'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ae305052523c05bacb294928c1f81afd4e51931
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41995539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a><span data-ttu-id="35f68-102">Création ou modification manuelle d’une règle de traduction dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35f68-102">Create or modify a translation rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35f68-103">_**Dernière modification de la rubrique :** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="35f68-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="35f68-104">Effectuez cette procédure si vous voulez définir une règle de traduction en écrivant une expression régulière pour le modèle correspondant et la règle de traduction.</span><span class="sxs-lookup"><span data-stu-id="35f68-104">Follow these steps if you want to define a translation rule by writing a regular expression for the matching pattern and translation rule.</span></span> <span data-ttu-id="35f68-105">Vous pouvez également entrer un ensemble de valeurs dans l’outil **créer une règle de traduction** et activer le panneau de configuration Lync Server pour générer le modèle de correspondance et la règle de traduction correspondants pour vous.</span><span class="sxs-lookup"><span data-stu-id="35f68-105">Alternatively, you can enter a set of values in the **Build a Translation Rule** tool and enable Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="35f68-106">Pour plus d’informations, voir [créer ou modifier une règle de traduction à l’aide de l’outil créer une règle de traduction dans Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span><span class="sxs-lookup"><span data-stu-id="35f68-106">For details, see [Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span></span>

<div>

## <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="35f68-107">Pour définir une règle de traduction manuellement</span><span class="sxs-lookup"><span data-stu-id="35f68-107">To define a translation rule manually</span></span>

1.  <span data-ttu-id="35f68-108">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="35f68-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="35f68-109">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="35f68-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="35f68-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="35f68-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="35f68-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="35f68-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="35f68-112">Pour commencer à définir une règle de traduction, suivez la procédure décrite dans [Configure a trunk with Media Bypass in Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) jusqu’à l’étape 10 ou [Configure a trunk without Media Bypass in Lync Server 2013 à l'](lync-server-2013-configure-a-trunk-without-media-bypass.md) étape 9.</span><span class="sxs-lookup"><span data-stu-id="35f68-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="35f68-113">Dans le champ **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.</span><span class="sxs-lookup"><span data-stu-id="35f68-113">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="35f68-114">(Facultatif) Dans **Description**, entrez la description de la règle de traduction, par exemple **Appel longue distance international**.</span><span class="sxs-lookup"><span data-stu-id="35f68-114">(Optional) In **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="35f68-115">Cliquez sur **Modifier** au bas de la section **Créer une règle de traduction**.</span><span class="sxs-lookup"><span data-stu-id="35f68-115">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

7.  <span data-ttu-id="35f68-116">Entrez ce qui suit dans **Taper une expression régulière** :</span><span class="sxs-lookup"><span data-stu-id="35f68-116">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="35f68-117">Dans **Suivre ce modèle**, spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire.</span><span class="sxs-lookup"><span data-stu-id="35f68-117">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
      - <span data-ttu-id="35f68-118">Dans **Règle de traduction**, spécifiez un modèle pour le format des numéros traduits.</span><span class="sxs-lookup"><span data-stu-id="35f68-118">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="35f68-119">Par exemple, si vous entrez \*\* ^ \\+ (\\d{9}\\d +) $\*\* dans la **correspondance de ce modèle** et **011 $1** dans la **règle de traduction**, la règle convertit + 441235551010 en 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="35f68-119">For example, if you enter **^\\+(\\d{9}\\d+)$** in **Match this pattern** and **011$1** in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

8.  <span data-ttu-id="35f68-120">Cliquez sur **OK** pour enregistrer la règle de traduction.</span><span class="sxs-lookup"><span data-stu-id="35f68-120">Click **OK** to save the translation rule.</span></span>

9.  <span data-ttu-id="35f68-121">Cliquez sur **OK** pour enregistrer la configuration de la jonction.</span><span class="sxs-lookup"><span data-stu-id="35f68-121">Click **OK** to save the trunk configuration.</span></span>

10. <span data-ttu-id="35f68-122">Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="35f68-122">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="35f68-123">Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="35f68-123">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="35f68-124">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="35f68-124">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="35f68-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="35f68-125">See Also</span></span>


[<span data-ttu-id="35f68-126">Création ou modification d’une règle de conversion à l’aide de l’outil créer une règle de traduction dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35f68-126">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[<span data-ttu-id="35f68-127">Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35f68-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="35f68-128">Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35f68-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="35f68-129">Publier les modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35f68-129">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="35f68-130">Options globales de déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35f68-130">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

