---
title: 'Lync Server 2013 : créer des objets contact pour la messagerie unifiée Exchange hébergée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c783a79c6d3ed3cd0af47d53d136a47585cb94d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="ec261-102">Créer des objets contact pour la messagerie unifiée Exchange hébergée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec261-102">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec261-103">_**Dernière modification de la rubrique :** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="ec261-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="ec261-104">La procédure suivante explique comment créer des objets Contact Standard automatique ou Accès abonné pour la messagerie unifiée Exchange hébergée.</span><span class="sxs-lookup"><span data-stu-id="ec261-104">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="ec261-105">Pour plus d’informations, reportez-vous à la rubrique [gestion des objets contact Exchange hébergés dans Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="ec261-105">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="ec261-106">Pour plus d’informations sur la configuration des objets contact, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="ec261-106">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="ec261-107">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="ec261-107">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="ec261-108">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="ec261-108">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="ec261-109">Avant que les objets contact Lync Server 2013 puissent être activés pour la messagerie unifiée Exchange hébergée, une stratégie de messagerie vocale hébergée qui s’applique à ces objets doit être déployée.</span><span class="sxs-lookup"><span data-stu-id="ec261-109">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="ec261-110">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-hosted-voice-mail-policies.md">stratégies de messagerie vocale hébergée dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ec261-110">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="ec261-111">Pour créer des objets Contact Standard automatique ou Accès abonné pour la messagerie unifiée Exchange hébergée</span><span class="sxs-lookup"><span data-stu-id="ec261-111">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="ec261-112">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ec261-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ec261-p102">Exécutez l’applet de commande New-CsExUmContact pour créer les objets Contact requis pour votre déploiement. Exécutez par exemple la commande suivante pour créer un objet Contact Standard automatique ou Accès abonné :</span><span class="sxs-lookup"><span data-stu-id="ec261-p102">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment. For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="ec261-115">Ces exemples définissent les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="ec261-115">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="ec261-116">**SipAddress** indique l’adresse SIP de l’objet Contact.</span><span class="sxs-lookup"><span data-stu-id="ec261-116">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="ec261-117">Cette adresse ne doit pas avoir déjà été utilisée pour configurer un objet Contact ou utilisateur dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ec261-117">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="ec261-118">Cette valeur doit être au format « SIP :\<*adresse*\>SIP », comme indiqué dans les exemples précédents.</span><span class="sxs-lookup"><span data-stu-id="ec261-118">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="ec261-119">**RegistrarPool** spécifie le nom de domaine complet du pool sur lequel le service de serveur d’inscriptions est exécuté.</span><span class="sxs-lookup"><span data-stu-id="ec261-119">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="ec261-120">Les objets contact de messagerie unifiée Exchange ne peuvent pas être déplacés vers des pools qui font partie de déploiements Lync Server 2013 antérieurs à Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ec261-120">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="ec261-121">**OU** spécifies l’unité d’organisation Active Directory dans laquelle cet objet Contact sera situé.</span><span class="sxs-lookup"><span data-stu-id="ec261-121">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="ec261-p104">**DisplayNumber** spécifie le numéro de téléphone de l’objet Contact. Le numéro de téléphone de chaque objet Contact doit être unique.</span><span class="sxs-lookup"><span data-stu-id="ec261-p104">**DisplayNumber** specifies the telephone number of the contact object. The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="ec261-p105">**AutoAttendant** indique si l’objet Contact est un standard automatique. Le standard automatique fournit un ensemble d’invites vocales qui permettent aux appelants de naviguer dans le système téléphonique et de joindre la personne désirée. Si ce paramètre est défini sur la valeur **False** (par défaut), cela indique un objet Contact Accès abonné.</span><span class="sxs-lookup"><span data-stu-id="ec261-p105">**AutoAttendant** specifies whether the Contact object is an Auto Attendant. Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact. A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

