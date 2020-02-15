---
title: 'Lync Server 2013 : configuration du mode de confidentialité améliorée de la présence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c16e33197ed28744df126d672385359f5eb8781b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a><span data-ttu-id="74469-102">Configuration du mode de confidentialité améliorée de la présence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74469-102">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74469-103">_**Dernière modification de la rubrique :** 2014-12-08_</span><span class="sxs-lookup"><span data-stu-id="74469-103">_**Topic Last Modified:** 2014-12-08_</span></span>

<span data-ttu-id="74469-104">Grâce au mode de confidentialité de la présence enrichie, les utilisateurs peuvent restreindre leur information de présence afin qu’ils soient visibles uniquement par les contacts répertoriés dans la liste de contacts Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="74469-104">With enhanced presence privacy mode, users can restrict their presence information so that it is visible only to the contacts listed in their Lync 2013 Contacts list.</span></span> <span data-ttu-id="74469-105">Les cmdlets **New-CsPrivacyConfiguration** et **Set-CsPrivacyConfiguration** ont un paramètre EnablePrivacyMode contrôle cette option.</span><span class="sxs-lookup"><span data-stu-id="74469-105">The **New-CsPrivacyConfiguration** and **Set-CsPrivacyConfiguration** cmdlets have an EnablePrivacyMode parameter controls this option.</span></span> <span data-ttu-id="74469-106">Lorsque EnablePrivacyMode est défini sur true, l’option de restriction des informations de présence aux contacts devient disponible dans les options d’état de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="74469-106">When EnablePrivacyMode is set to True, the option to restrict presence information to contacts becomes available in the Lync 2013 Status options.</span></span> <span data-ttu-id="74469-107">Lorsque l’option EnablePrivacyMode est définie sur False, les utilisateurs peuvent choisir de toujours autoriser les utilisateurs à consulter leurs informations de présence ou d’accepter toutes les futures modifications que l’administrateur apporte au mode de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="74469-107">When EnablePrivacyMode is set to False, users can choose either to always allow everyone to see their presence information or to adhere to any future changes the administrator makes to the privacy mode.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="74469-108">Les paramètres de confidentialité de Lync 2013 et Lync 2010 ne sont pas honorés par les versions antérieures (Microsoft Office Communicator 2007 R2 ou Microsoft Office Communicator 2007).</span><span class="sxs-lookup"><span data-stu-id="74469-108">Lync 2013 and Lync 2010 privacy settings are not honored by previous versions (Microsoft Office Communicator 2007 R2 or Microsoft Office Communicator 2007).</span></span> <span data-ttu-id="74469-109">Si les versions précédentes d’Office Communicator sont autorisées à se connecter, le statut de l’utilisateur Lync 2013, les informations de contact ou l’image peuvent être affichés par une personne qui n’a pas été autorisée à l’afficher.</span><span class="sxs-lookup"><span data-stu-id="74469-109">If previous versions of Office Communicator are allowed to sign in, a Lync 2013 user’s status, contact information, or picture could be viewed by someone who has not been authorized to view it.</span></span> <span data-ttu-id="74469-110">De plus, les paramètres de confidentialité de l’utilisateur Lync 2013 sont réinitialisés s’il se connecte ultérieurement à l’aide d’une version précédente de Communicator.</span><span class="sxs-lookup"><span data-stu-id="74469-110">Additionally, a Lync 2013 user’s privacy settings are reset if he or she later signs in with previous version of Communicator.</span></span><BR><span data-ttu-id="74469-111">Pour ces raisons, dans un scénario de migration, avant de pouvoir activer le mode de confidentialité améliorée de la présence :</span><span class="sxs-lookup"><span data-stu-id="74469-111">For these reasons, in a migration scenario, before you enable enhanced presence privacy mode:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="74469-112">Assurez-vous que Lync 2013 est installé sur chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="74469-112">Ensure that every user has Lync 2013 installed.</span></span></P>
> <LI>
> <P><span data-ttu-id="74469-113">Définissez une règle de stratégie de version de client empêchant les versions précédentes de Communicator de se connecter.</span><span class="sxs-lookup"><span data-stu-id="74469-113">Define a client version policy rule to prevent previous versions of Communicator from signing in.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a><span data-ttu-id="74469-114">Pour activer le mode de confidentialité améliorée de la présence</span><span class="sxs-lookup"><span data-stu-id="74469-114">To enable enhanced presence privacy mode</span></span>

1.  <span data-ttu-id="74469-115">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="74469-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="74469-116">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="74469-116">Run the following command:</span></span>
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    <span data-ttu-id="74469-117">Cette commande active le mode confidentialité pour tous les paramètres de confidentialité utilisés actuellement dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="74469-117">This command enables privacy mode for all the privacy configuration settings currently in use in the organization.</span></span> <span data-ttu-id="74469-118">Pour plus d’informations sur la façon dont les configurations de stratégie de mode de confidentialité de la présence améliorée de Lync Server gère la présence du contact pour le client Lync 2013, voir l’article de la base de connaissances Microsoft [activation du mode de confidentialité Enhanced presence de Lync Server met à jour l’état de présence de certains contacts Lync sur « indisponible »](http://support.microsoft.com/kb/3020057).</span><span class="sxs-lookup"><span data-stu-id="74469-118">For more information about how the Lync Server enhanced presence privacy mode policy configurations manages contact presence for the Lync 2013 client, see the Microsoft KB article [Enabling Lync Server enhanced presence privacy mode updates the presence status of some Lync contacts to "unavailable"](http://support.microsoft.com/kb/3020057).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="74469-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="74469-119">See Also</span></span>


[<span data-ttu-id="74469-120">Get-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="74469-120">Get-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[<span data-ttu-id="74469-121">New-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="74469-121">New-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[<span data-ttu-id="74469-122">Set-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="74469-122">Set-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

