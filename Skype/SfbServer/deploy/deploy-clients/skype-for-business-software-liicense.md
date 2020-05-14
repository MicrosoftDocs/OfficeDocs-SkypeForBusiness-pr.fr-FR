---
title: Licence du logiciel Skype Room System Skype entreprise
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lisez cette rubrique pour savoir comment vérifier si vous disposez d’une licence en volume de Skype entreprise.
ms.openlocfilehash: a44e95d8cd488e2b12e03ee9848ef3d1b254180c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220924"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="768a3-103">Skype Room System : licence du logiciel Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="768a3-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="768a3-104">Lisez cette rubrique pour savoir comment vérifier si vous disposez d’une licence en volume de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="768a3-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="768a3-105">Skype Room System utilise un client Skype entreprise installé, qui nécessite une licence en volume logiciel.</span><span class="sxs-lookup"><span data-stu-id="768a3-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="768a3-106">Avant de déployer le premier système Skype Room, recherchez l’état de la licence en volume du déploiement à l’aide des serveurs de gestion de clés (KMS) ou des clés d’activation multiples (MAK).</span><span class="sxs-lookup"><span data-stu-id="768a3-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="768a3-107">Serveurs de gestion de clés (KMS)</span><span class="sxs-lookup"><span data-stu-id="768a3-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="768a3-108">Si KMS est en place et distribuera les activations de licence en volume Skype entreprise, le système Skype Room activera automatiquement le client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="768a3-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="768a3-109">Pour savoir si KMS est en place :</span><span class="sxs-lookup"><span data-stu-id="768a3-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="768a3-110">À partir d’une invite de commandes, exécutez :`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="768a3-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="768a3-111">Pour plus d’informations, consultez [la rubrique Comment découvrir les hôtes KMS Office et Windows via DNS et supprimer les instances non autorisées](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="768a3-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="768a3-112">Pour configurer un KMS, voir [activation kms d’office 2013](https://technet.microsoft.com/library/ee624357.aspx) et [GVLK pour kms et activation Active Directory d’Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="768a3-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="768a3-113">La clé de licence en volume générique Office 2013 pour Lync : 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (cette clé force Skype Room System à rechercher un KMS sur le réseau.)</span><span class="sxs-lookup"><span data-stu-id="768a3-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="768a3-114">Clés d’activation multiple (MAK) à partir du centre de service de licences en volume (VLSC)</span><span class="sxs-lookup"><span data-stu-id="768a3-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="768a3-115">Si le client utilise un autre logiciel de licence en volume, le service informatique gère les activations logicielles et le contrat de licence en volume (VLA) à l’aide du VLSC.</span><span class="sxs-lookup"><span data-stu-id="768a3-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="768a3-116">Cela permettra également à l’entreprise d’acheter des activations de licence en volume Skype entreprise, après quoi la société peut obtenir une MAK pour entrée dans la console d’administration de Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="768a3-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="768a3-117">Un client avec un VLA doit connaître ses informations d’identification VLSC, qui seront utilisées pour administrer le contrat et obtenir une MAK.</span><span class="sxs-lookup"><span data-stu-id="768a3-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="768a3-118">Si ce n’est pas le cas, le service financier du client doit être en mesure de confirmer si le client a payé un VLA.</span><span class="sxs-lookup"><span data-stu-id="768a3-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="768a3-119">Pour obtenir une MAK, accédez au centre de gestion des licences en volume pour afficher les accords et télécharger des clés de produit (MAK).</span><span class="sxs-lookup"><span data-stu-id="768a3-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="768a3-120">Pour plus d’informations, accédez au [Centre](https://www.microsoft.com/Licensing/servicecenter/default.aspx)de gestion des licences en volume.</span><span class="sxs-lookup"><span data-stu-id="768a3-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a><span data-ttu-id="768a3-121">MAK pour Microsoft 365 ou Office 365 sans accès VLSC</span><span class="sxs-lookup"><span data-stu-id="768a3-121">MAK for Microsoft 365 or Office 365 without VLSC access</span></span>

<span data-ttu-id="768a3-122">Si le client ne dispose pas d’un contrat de licence en volume, les activations de Skype entreprise seront plus difficiles à gérer.</span><span class="sxs-lookup"><span data-stu-id="768a3-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="768a3-123">Toutefois, les clients Microsoft 365 et Office 365 sans accès VLSC peuvent obtenir une MAK promotionnelle en fournissant les informations suivantes à l’OEM vendant Skype Room System :</span><span class="sxs-lookup"><span data-stu-id="768a3-123">However, Microsoft 365 and Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="768a3-124">Nom de la société</span><span class="sxs-lookup"><span data-stu-id="768a3-124">Company name</span></span>
    
- <span data-ttu-id="768a3-125">Nom, adresse de messagerie et numéro de téléphone du contact de déploiement</span><span class="sxs-lookup"><span data-stu-id="768a3-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="768a3-126">Nombre de systèmes déployés</span><span class="sxs-lookup"><span data-stu-id="768a3-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="768a3-127">Date de déploiement</span><span class="sxs-lookup"><span data-stu-id="768a3-127">Deployment date</span></span>
    
- <span data-ttu-id="768a3-128">Si le client a un responsable de compte technique Microsoft, le nom et les informations de contact du TAM</span><span class="sxs-lookup"><span data-stu-id="768a3-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

