---
title: 'Lync Server 2013: configuration du mode de confidentialité Enhanced presence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 878691cd7b39d893b416a128f937d2aad1e561b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a><span data-ttu-id="3ba35-102">Configuration du mode de confidentialité Enhanced presence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ba35-102">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ba35-103">_**Dernière modification de la rubrique:** 2014-12-08_</span><span class="sxs-lookup"><span data-stu-id="3ba35-103">_**Topic Last Modified:** 2014-12-08_</span></span>

<span data-ttu-id="3ba35-104">Le mode de confidentialité Enhanced presence permet aux utilisateurs de limiter les informations de présence de sorte qu’il ne soit visible que par les contacts répertoriés dans la liste de contacts Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3ba35-104">With enhanced presence privacy mode, users can restrict their presence information so that it is visible only to the contacts listed in their Lync 2013 Contacts list.</span></span> <span data-ttu-id="3ba35-105">Les applets de commande **New-CsPrivacyConfiguration** et **Set-CsPrivacyConfiguration** disposent d’un paramètre EnablePrivacyMode Control de cette option.</span><span class="sxs-lookup"><span data-stu-id="3ba35-105">The **New-CsPrivacyConfiguration** and **Set-CsPrivacyConfiguration** cmdlets have an EnablePrivacyMode parameter controls this option.</span></span> <span data-ttu-id="3ba35-106">Lorsque EnablePrivacyMode est défini sur true, l’option permettant de limiter les informations de présence aux contacts devient disponible dans les options d’état de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3ba35-106">When EnablePrivacyMode is set to True, the option to restrict presence information to contacts becomes available in the Lync 2013 Status options.</span></span> <span data-ttu-id="3ba35-107">Lorsque EnablePrivacyMode est défini sur false, les utilisateurs peuvent choisir de toujours autoriser tout le monde à voir leurs informations de présence ou à se conformer à toute modification ultérieure apportée par l’administrateur au mode de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="3ba35-107">When EnablePrivacyMode is set to False, users can choose either to always allow everyone to see their presence information or to adhere to any future changes the administrator makes to the privacy mode.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3ba35-108">Les paramètres de confidentialité de Lync 2013 et de Lync 2010 ne respectent pas les versions précédentes (Microsoft Office Communicator 2007 R2 ou Microsoft Office Communicator 2007).</span><span class="sxs-lookup"><span data-stu-id="3ba35-108">Lync 2013 and Lync 2010 privacy settings are not honored by previous versions (Microsoft Office Communicator 2007 R2 or Microsoft Office Communicator 2007).</span></span> <span data-ttu-id="3ba35-109">Si les versions précédentes d’Office Communicator sont autorisées à se connecter, l’état de l’utilisateur de Lync 2013, ses informations de contact ou son image peuvent être affichés par une personne qui n’a pas été autorisée à le consulter.</span><span class="sxs-lookup"><span data-stu-id="3ba35-109">If previous versions of Office Communicator are allowed to sign in, a Lync 2013 user’s status, contact information, or picture could be viewed by someone who has not been authorized to view it.</span></span> <span data-ttu-id="3ba35-110">De plus, les paramètres de confidentialité de l’utilisateur de Lync 2013 sont réinitialisés s’il se connecte par la suite à une version antérieure de Communicator.</span><span class="sxs-lookup"><span data-stu-id="3ba35-110">Additionally, a Lync 2013 user’s privacy settings are reset if he or she later signs in with previous version of Communicator.</span></span><BR><span data-ttu-id="3ba35-111">C’est pour ces raisons qu’il s’agit d’un scénario de migration avant d’activer le mode de confidentialité Enhanced PRESENCE:</span><span class="sxs-lookup"><span data-stu-id="3ba35-111">For these reasons, in a migration scenario, before you enable enhanced presence privacy mode:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="3ba35-112">Assurez-vous que tous les utilisateurs disposent de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3ba35-112">Ensure that every user has Lync 2013 installed.</span></span></P>
> <LI>
> <P><span data-ttu-id="3ba35-113">Définissez une règle de stratégie de version de client pour empêcher les versions précédentes de Communicator de se connecter.</span><span class="sxs-lookup"><span data-stu-id="3ba35-113">Define a client version policy rule to prevent previous versions of Communicator from signing in.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a><span data-ttu-id="3ba35-114">Pour activer le mode de confidentialité Enhanced presence</span><span class="sxs-lookup"><span data-stu-id="3ba35-114">To enable enhanced presence privacy mode</span></span>

1.  <span data-ttu-id="3ba35-115">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3ba35-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3ba35-116">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="3ba35-116">Run the following command:</span></span>
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    <span data-ttu-id="3ba35-117">Cette commande active le mode de confidentialité pour tous les paramètres de configuration de confidentialité actuellement utilisés au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="3ba35-117">This command enables privacy mode for all the privacy configuration settings currently in use in the organization.</span></span> <span data-ttu-id="3ba35-118">Pour plus d’informations sur la façon dont les configurations de la stratégie de fonctionnement du mode de confidentialité de Lync Server Enhanced s’adressent à la présence du contact pour le client Lync 2013, consultez l’article de la base de connaissances Microsoft [activation du mode de confidentialité de présence améliorée de Lync Server. État de certains contacts Lync en «indisponible»](http://support.microsoft.com/kb/3020057).</span><span class="sxs-lookup"><span data-stu-id="3ba35-118">For more information about how the Lync Server enhanced presence privacy mode policy configurations manages contact presence for the Lync 2013 client, see the Microsoft KB article [Enabling Lync Server enhanced presence privacy mode updates the presence status of some Lync contacts to "unavailable"](http://support.microsoft.com/kb/3020057).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3ba35-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3ba35-119">See Also</span></span>


[<span data-ttu-id="3ba35-120">Get-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="3ba35-120">Get-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[<span data-ttu-id="3ba35-121">Nouveau-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="3ba35-121">New-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[<span data-ttu-id="3ba35-122">Set-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="3ba35-122">Set-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

