---
title: 'Lync Server 2013 : création ou modification d’un objet contact de téléphone de partie commune'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 418001642f387caf67277f408d4eb19109c98936
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="f78ee-102">Création ou modification d’un objet contact de téléphone de partie commune dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f78ee-102">Create or modify a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f78ee-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="f78ee-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="f78ee-104">Pour créer des objets contact des services de domaine Active Directory pour tous vos téléphones de partie commune, utilisez la cmdlet **New-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="f78ee-104">To create Active Directory Domain Services contact objects for all your common area phones, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="f78ee-105">Cette applet de commande peut créer des objets contact à utiliser avec des téléphones de partie commune ou associer des objets contact existants à un nouveau téléphone de partie commune.</span><span class="sxs-lookup"><span data-stu-id="f78ee-105">This cmdlet can either create new contact objects for use with common area phones, or it can associate existing contact objects with a new common area phone.</span></span> <span data-ttu-id="f78ee-106">Pour modifier les propriétés des objets contact associés à des téléphones de partie commune, utilisez la cmdlet **Set-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="f78ee-106">To modify the properties of the contact objects associated with common area phones, use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="f78ee-107">Les paramètres facultatifs de **Set-CsCommonAreaPhone** vous permettent de modifier des éléments, tels que le nom d’affichage du contact Active Directory ou l’URI (Uniform Resource Identifier) de ligne associé au téléphone, ainsi que d’activer et de désactiver le compte à utiliser avec Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f78ee-107">Optional parameters for **Set-CsCommonAreaPhone** enable you to change items, such as the contact’s Active Directory display name or the line Uniform Resource Identifier (URI) associated with the phone, and enable and disable the account for use with Lync Server.</span></span> <span data-ttu-id="f78ee-108">Pour plus d’informations sur toutes les modifications disponibles, reportez-vous à la section Parameters de [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="f78ee-108">For details about all the available modifications, see the Parameters section at [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span></span> <span data-ttu-id="f78ee-109">Pour plus d’informations sur les paramètres **New-CsCommonAreaPhone** , voir [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="f78ee-109">For details about **New-CsCommonAreaPhone** parameters, see [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span></span>

<span data-ttu-id="f78ee-110">Vous pouvez exécuter ces deux cmdlets à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f78ee-110">You can run these two cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f78ee-111">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="f78ee-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a><span data-ttu-id="f78ee-112">Création d’un objet contact de téléphone de partie commune</span><span class="sxs-lookup"><span data-stu-id="f78ee-112">Creating a common area phone contact object</span></span>

  - <span data-ttu-id="f78ee-113">Pour créer un objet contact de téléphone de partie commune, utilisez la cmdlet **New-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="f78ee-113">To create a new common area phone contact object, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="f78ee-114">Au minimum, vous devez fournir les informations suivantes lors de la création d’un objet contact :</span><span class="sxs-lookup"><span data-stu-id="f78ee-114">At a minimum, you must supply the following information when creating a contact object:</span></span>
    
      - <span data-ttu-id="f78ee-115">**LineURI**: numéro de téléphone attribué au téléphone de partie commune.</span><span class="sxs-lookup"><span data-stu-id="f78ee-115">**LineUri**: The telephone number assigned to the common area phone.</span></span> <span data-ttu-id="f78ee-116">Notez que vous devez utiliser le format E. 164 lorsque vous spécifiez le numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="f78ee-116">Note that you must use the E.164 format when specifying the phone number.</span></span>
    
      - <span data-ttu-id="f78ee-117">**RegistrarPool**: nom de domaine complet (FQDN) du pool de serveurs d’inscriptions qui hébergera l’objet contact.</span><span class="sxs-lookup"><span data-stu-id="f78ee-117">**RegistrarPool**: The fully qualified domain name (FQDN) of the Registrar pool that will host the contact object.</span></span>
    
      - <span data-ttu-id="f78ee-118">**Ou**: nom unique du conteneur Active Directory dans lequel l’objet contact sera créé.</span><span class="sxs-lookup"><span data-stu-id="f78ee-118">**OU**: Distinguished name of the Active Directory container where the contact object will be created.</span></span>
    
    <span data-ttu-id="f78ee-119">Nous vous recommandons également de fournir un nom complet des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f78ee-119">We also recommend that you provide an Active Directory Domain Services display name.</span></span> <span data-ttu-id="f78ee-120">Dans le cas contraire, vous devrez utiliser un GUID pour spécifier l’identité de téléphone.</span><span class="sxs-lookup"><span data-stu-id="f78ee-120">Otherwise, you will need to use a GUID to specify the phone Identity.</span></span> <span data-ttu-id="f78ee-121">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f78ee-121">For example:</span></span>
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a><span data-ttu-id="f78ee-122">Modification d’un objet contact de téléphone de partie commune</span><span class="sxs-lookup"><span data-stu-id="f78ee-122">Modifying a common area phone contact object</span></span>

  - <span data-ttu-id="f78ee-123">Pour modifier les propriétés d’un téléphone de partie commune existant, l’objet contact utilise la cmdlet **Set-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="f78ee-123">To modify the properties of an existing common area phone, contact object use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="f78ee-124">Par exemple, cette commande configure l’adresse SIP pour le téléphone de partie commune avec la salle d’attente DisplayName :</span><span class="sxs-lookup"><span data-stu-id="f78ee-124">For example, this command configures the SIP address for the common area phone with the DisplayName Lobby:</span></span>
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

<span data-ttu-id="f78ee-125">Pour plus d’informations, reportez-vous aux rubriques d’aide pour la cmdlet [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) et la cmdlet [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="f78ee-125">For details, see the Help topics for the [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) cmdlet and the [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

