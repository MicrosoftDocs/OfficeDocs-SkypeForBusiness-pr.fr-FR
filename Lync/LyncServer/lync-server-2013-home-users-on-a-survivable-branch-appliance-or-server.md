---
title: 'Lync Server 2013 : utilisateurs domestiques sur un Survivable Branch Appliance ou un serveur Survivable Branch Server'
description: 'Lync Server 2013 : utilisateurs domestiques sur un Survivable Branch Appliance ou un serveur Survivable Branch Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 124eb7a51a8d5ff672d720fdad8956f682e29090
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552780"
---
# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="06347-103">Utilisateurs domestiques sur un Survivable Branch Appliance ou un serveur Survivable Branch Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06347-103">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06347-104">_**Dernière modification de la rubrique :** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="06347-104">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="06347-105">Le processus d’hébergement des utilisateurs sur un Survivable Branch Appliance ou un serveur Survivable Branch Server est semblable à celui de l’hébergement des utilisateurs sur un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="06347-105">The process of homing users on a Survivable Branch Appliance or a Survivable Branch Server is similar to the process of homing users on a Front End pool.</span></span> <span data-ttu-id="06347-106">Effectuez la procédure Survivable Branch Appliance ou le serveur Survivable Branch Server sur le site central.</span><span class="sxs-lookup"><span data-stu-id="06347-106">Perform the Survivable Branch Appliance or Survivable Branch Server procedure at the central site.</span></span>

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="06347-107">Pour héberger des utilisateurs sur un Survivable Branch Appliance ou sur un serveur Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="06347-107">To home users on Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="06347-108">Avant de transférer des utilisateurs vers le Survivable Branch Server ou le serveur Survivable Branch Server, ouvrez Lync Server Management Shell, puis effectuez toutes les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="06347-108">Before moving users to the Survivable Branch Server or Survivable Branch Server, open the Lync Server Management Shell, and then do all of the following:</span></span>
    
      - <span data-ttu-id="06347-109">Exécutez l’applet de commande **test-CsPstnOutboundCall** pour vérifier que le serveur Survivable Branch Server est en cours d’exécution et que la connectivité PSTN (réseau téléphonique commuté) est configurée.</span><span class="sxs-lookup"><span data-stu-id="06347-109">Run the cmdlet **Test-CsPstnOutboundCall** to verify that the Survivable Branch Server is running and that the public switched telephone network (PSTN) connectivity is configured.</span></span> <span data-ttu-id="06347-110">Si vous avez besoin de modifier les propriétés de la passerelle PSTN, utilisez la **Set-CsPstnGateway**.</span><span class="sxs-lookup"><span data-stu-id="06347-110">If you need to modify PSTN gateway properties, use the cmdlet **Set-CsPstnGateway**.</span></span>
    
      - <span data-ttu-id="06347-111">Exécutez l’applet de commande **Get-CsVoicePolicy** pour vérifier que les utilisateurs qui seront hébergés sur le serveur Survivable Branch Server possèdent la stratégie de routage VoIP appropriée.</span><span class="sxs-lookup"><span data-stu-id="06347-111">Run the cmdlet **Get-CsVoicePolicy** to verify that the users who will be homed on the Survivable Branch Server have the appropriate VoIP routing policy.</span></span> <span data-ttu-id="06347-112">Si vous avez besoin de modifier la stratégie VoIP, utilisez la cmdlet **Set-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="06347-112">If you need to modify the VoIP policy, use the cmdlet **Set-CsVoicePolicy**.</span></span>
    
      - <span data-ttu-id="06347-113">Exécutez la **Get-CsVoicemailReroutingConfiguration** pour vérifier que les paramètres de réacheminement de la messagerie vocale sont configurés.</span><span class="sxs-lookup"><span data-stu-id="06347-113">Run the cmdlet **Get-CsVoicemailReroutingConfiguration** to verify that the voice mail rerouting settings are configured.</span></span> <span data-ttu-id="06347-114">Si vous avez besoin de modifier les paramètres de réacheminement de la messagerie vocale, utilisez la cmdlet **Set-CsVoicemailReroutingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="06347-114">If you need to modify the voice mail rerouting settings, use the cmdlet **Set-CsVoicemailReroutingConfiguration**.</span></span>

2.  <span data-ttu-id="06347-115">Dans Lync Server Management Shell, exécutez l’applet de commande **Move-Csuser** pour déplacer les utilisateurs d’accueil.</span><span class="sxs-lookup"><span data-stu-id="06347-115">In the Lync Server Management Shell, run the cmdlet **Move-CsUser** to move home users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="06347-116">Vous pouvez également utiliser le panneau de configuration Lync Server pour vérifier les conditions préalables et les utilisateurs domestiques.</span><span class="sxs-lookup"><span data-stu-id="06347-116">You can also use Lync Server Control Panel to verify prerequisites and home users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="06347-117">Les utilisateurs hébergés sur une appliance Survivable Branch Lync Server ne peuvent pas créer de nouvelles salles de conversation ni afficher la carte de salle pour les salles existantes.</span><span class="sxs-lookup"><span data-stu-id="06347-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="06347-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="06347-118">See Also</span></span>


[<span data-ttu-id="06347-119">Test-CsPstnOutboundCall</span><span class="sxs-lookup"><span data-stu-id="06347-119">Test-CsPstnOutboundCall</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[<span data-ttu-id="06347-120">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="06347-120">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="06347-121">Get-CsVoicemailReroutingConfiguration</span><span class="sxs-lookup"><span data-stu-id="06347-121">Get-CsVoicemailReroutingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[<span data-ttu-id="06347-122">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="06347-122">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

