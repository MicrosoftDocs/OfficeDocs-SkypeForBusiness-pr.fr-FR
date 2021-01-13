---
title: Licence logicielle Skype Room System Skype Entreprise
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lisez cette rubrique pour savoir comment vérifier si vous avez une licence en volume de logiciel Skype Entreprise.
ms.openlocfilehash: 20e04f69ba5a931bae6ac8598567165a7a6043a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833924"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="cd777-103">Skype Room System : licence logicielle Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="cd777-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="cd777-104">Lisez cette rubrique pour savoir comment vérifier si vous avez une licence en volume de logiciel Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="cd777-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="cd777-105">Skype Room System utilise un client Skype Entreprise installé, qui nécessite une licence en volume logicielle.</span><span class="sxs-lookup"><span data-stu-id="cd777-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="cd777-106">Avant de déployer le premier skype room system, découvrez l’état de la licence en volume du déploiement , à l’aide des serveurs de gestion de clés (KMS) ou des clés d’activation multiples (MAK).</span><span class="sxs-lookup"><span data-stu-id="cd777-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="cd777-107">Serveurs de gestion de clés (KMS)</span><span class="sxs-lookup"><span data-stu-id="cd777-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="cd777-108">Si le service KMS est en place et distribue les activations de licence en volume Skype Entreprise, Skype Room System active automatiquement le client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="cd777-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="cd777-109">Pour savoir si kmS est en place :</span><span class="sxs-lookup"><span data-stu-id="cd777-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="cd777-110">À partir d’une invite de commandes, exécutez :  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="cd777-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="cd777-111">Pour plus d’informations, voir Comment découvrir les hôtes KMS Office et [Windows via DNS et supprimer des instances non autorisées](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="cd777-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="cd777-112">Pour configurer un service KMS, consultez [l’activation KMS d’Office 2013](https://technet.microsoft.com/library/ee624357.aspx) et des clés GVK pour l’activation KMS et [Active Directory d’Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="cd777-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="cd777-113">Clé de licence en volume générique Office 2013 pour Lync : 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (cette clé entraîne la recherche d’un service KMS sur le réseau par Skype Room System).)</span><span class="sxs-lookup"><span data-stu-id="cd777-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="cd777-114">Clés d’activation multiples (MAK) à partir du Centre de service de licence en volume (VLSC)</span><span class="sxs-lookup"><span data-stu-id="cd777-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="cd777-115">Si le client utilise un autre logiciel de licence en volume, le service informatique gère les activations logicielles et le contrat de licence en volume (VLA) à l’aide du VLSC.</span><span class="sxs-lookup"><span data-stu-id="cd777-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="cd777-116">Cela permettra également à l’entreprise d’acheter des activations VL Skype Entreprise, après quoi elle peut obtenir une clé MAK pour l’entrée dans la console d’administration Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="cd777-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="cd777-117">Un client avec un VLA doit connaître ses informations d’identification VLSC, qui seront utilisées pour administrer le contrat et obtenir une mak.</span><span class="sxs-lookup"><span data-stu-id="cd777-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="cd777-118">En cas de doute, le service financier du client doit être en mesure de confirmer si le client a payé un VLA.</span><span class="sxs-lookup"><span data-stu-id="cd777-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="cd777-119">Pour obtenir une clé MAK, accédez au Centre de gestion des licences en volume pour afficher les contrats et télécharger les clés de produit (MAK).</span><span class="sxs-lookup"><span data-stu-id="cd777-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="cd777-120">Pour plus d’informations, voir le Centre de gestion des [licences en volume.](https://www.microsoft.com/Licensing/servicecenter/default.aspx)</span><span class="sxs-lookup"><span data-stu-id="cd777-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a><span data-ttu-id="cd777-121">MAK pour Microsoft 365 ou Office 365 sans accès VLSC</span><span class="sxs-lookup"><span data-stu-id="cd777-121">MAK for Microsoft 365 or Office 365 without VLSC access</span></span>

<span data-ttu-id="cd777-122">Si le client n’a pas de contrat de licence en volume, les activations skype entreprise seront beaucoup plus difficiles à gérer.</span><span class="sxs-lookup"><span data-stu-id="cd777-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="cd777-123">Toutefois, les clients Microsoft 365 et Office 365 qui n’ont pas accès au VLSC peuvent obtenir une mak promotionnelle en fournissant les informations suivantes au OEM qui vend Skype Room System :</span><span class="sxs-lookup"><span data-stu-id="cd777-123">However, Microsoft 365 and Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="cd777-124">Nom de la société</span><span class="sxs-lookup"><span data-stu-id="cd777-124">Company name</span></span>
    
- <span data-ttu-id="cd777-125">Nom, adresse e-mail et numéro de téléphone du contact de déploiement</span><span class="sxs-lookup"><span data-stu-id="cd777-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="cd777-126">Nombre de systèmes déployés</span><span class="sxs-lookup"><span data-stu-id="cd777-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="cd777-127">Date de déploiement</span><span class="sxs-lookup"><span data-stu-id="cd777-127">Deployment date</span></span>
    
- <span data-ttu-id="cd777-128">Si le client dispose d’un gestionnaire de compte technique Microsoft, le nom et les informations de contact du responsable technique de l’analyseur technique</span><span class="sxs-lookup"><span data-stu-id="cd777-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

