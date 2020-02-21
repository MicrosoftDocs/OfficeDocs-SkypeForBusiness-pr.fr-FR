---
title: 'Lync Server 2013 : configuration des paramètres de réacheminement de la messagerie vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f327bfc533b28313e4728b13c7a69d6c16bc034
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a><span data-ttu-id="5ed36-102">Configurer les paramètres de réacheminement de la messagerie vocale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ed36-102">Configure voice mail rerouting settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ed36-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="5ed36-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="5ed36-104">Survivable Branch Appliances et les serveurs Survivable Branch Server peuvent assurer la survivabilité de la messagerie vocale pour les utilisateurs de succursale lors d’une panne de réseau étendu, si la messagerie unifiée Exchange est installée sur le site central et qu’un standard automatique de message de messagerie unifiée Exchange (AA) est déployé.</span><span class="sxs-lookup"><span data-stu-id="5ed36-104">Survivable Branch Appliances and Survivable Branch Servers can provide voice mail survivability for branch users during a WAN outage, if Exchange Unified Messaging (UM) is installed at the central site and an Exchange UM Message Auto Attendant (AA) is deployed.</span></span> <span data-ttu-id="5ed36-105">Nous conseillons que votre administrateur Exchange configure le standard automatique de manière à accepter uniquement les messages, ce qui désactive d’autres fonctionnalités génériques telles que le transfert vers un utilisateur ou un opérateur.</span><span class="sxs-lookup"><span data-stu-id="5ed36-105">We recommend that your Exchange administrator configure the AA to accept messages only, which disables other generic functionality, such as transfer to a user or transfer to an operator.</span></span> <span data-ttu-id="5ed36-106">Vous pouvez également utiliser un standard automatique générique ou personnaliser pour acheminer l’appel.</span><span class="sxs-lookup"><span data-stu-id="5ed36-106">Alternatively, you might use a generic AA or an AA customized to route the call.</span></span>

<span data-ttu-id="5ed36-107">Pour plus d’informations, reportez-vous à la section « Préparation de la survivabilité de la messagerie vocale » de la rubrique [Configuration requise pour la résistance des sites de succursale pour Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="5ed36-107">For details, see the “Preparing for Voice Mail Survivability” section of [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="to-configure-voice-mail-survivability"></a><span data-ttu-id="5ed36-108">Pour configurer la survivabilité de la messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="5ed36-108">To configure voice mail survivability</span></span>

1.  <span data-ttu-id="5ed36-109">Demandez à votre administrateur Exchange de configurer le AA de sorte qu’il accepte uniquement les messages (dans l’environnement Exchange Shell, utilisez l’applet de commande suivante : **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**.</span><span class="sxs-lookup"><span data-stu-id="5ed36-109">Ask your Exchange administrator to configure the AA to accept messages only (in the Exchange Shell use the following cmdlet: **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**.</span></span> <span data-ttu-id="5ed36-110">Le paramètre qui spécifie de laisser des messages (*SendVoiceMsgEnabled*) a la valeur True par défaut.</span><span class="sxs-lookup"><span data-stu-id="5ed36-110">The parameter that specifies to allow leaving messages (*SendVoiceMsgEnabled*) is true by default.</span></span>

2.  <span data-ttu-id="5ed36-111">Dans Lync Server Management Shell, utilisez la cmdlet **New-CSVoiceMailReroutingConfiguration** pour définir le numéro de téléphone AA comme numéro de téléphone du standard automatique de messagerie unifiée Exchange dans la configuration de réacheminement de la messagerie vocale sur le Survivable Branch Appliance ou le serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="5ed36-111">In the Lync Server Management Shell, use the **New-CSVoiceMailReroutingConfiguration** cmdlet to set the AA phone number as the Exchange UM Auto Attendant phone number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ed36-112">Si vous avez besoin de modifier le paramètre de réacheminement de la messagerie vocale ultérieurement, utilisez pour cela l’applet de commande <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5ed36-112">If you need to modify the voice mail rerouting setting later, use the <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> cmdlet to do so.</span></span> <span data-ttu-id="5ed36-113">Pour plus d’informations sur <STRONG>New-</STRONG> et <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, voir les rubriques d’aide du Shell.</span><span class="sxs-lookup"><span data-stu-id="5ed36-113">For details, about <STRONG>New-</STRONG> and <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, in the Shell Help topics.</span></span>

    
    </div>

3.  <span data-ttu-id="5ed36-114">Définissez le numéro d’accès abonné de messagerie unifiée Exchange correspondant au plan de numérotation de messagerie unifiée Exchange de l’utilisateur de la succursale comme numéro d’accès abonné de messagerie unifiée Exchange dans la configuration de réacheminement de la messagerie vocale sur le Survivable Branch Appliance ou le serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="5ed36-114">Set the Exchange UM subscriber access number that corresponds to the branch user’s Exchange UM dial plan as the Exchange UM subscriber access number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ed36-115">Configurez le plan de numérotation des utilisateurs de messagerie unifiée Exchange de sorte qu’il n’existe qu’un seul plan de numérotation associé à tous les utilisateurs de succursale qui ont besoin d’accéder à la fonctionnalité obtenir la messagerie vocale lors d’une panne de réseau étendu.</span><span class="sxs-lookup"><span data-stu-id="5ed36-115">Configure the Exchange UM users’ dial plan so that there is only one dial plan associated with all branch users who need access to the Get Voice Mail functionality during a WAN outage.</span></span>

    
    </div>

<span data-ttu-id="5ed36-116">**Étape suivante** pour Survivable Branch Appliances ou les serveurs Survivable Branch Server : [utilisateurs à domicile sur un Survivable Branch Appliance ou un serveur Survivable Branch Server dans Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="5ed36-116">**Next step** for Survivable Branch Appliances or Survivable Branch Servers: [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

