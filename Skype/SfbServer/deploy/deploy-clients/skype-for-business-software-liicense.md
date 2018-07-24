---
title: Skype salle système Skype pour la licence du logiciel Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Consultez cette rubrique pour découvrir comment procéder pour vérifier si vous disposez d’une licence en volume de Skype Entreprise.
ms.openlocfilehash: ba582174483eb511387ae085aba97d02631665fc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965421"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="05d4c-103">Skype Room System : licence du logiciel Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="05d4c-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="05d4c-104">Consultez cette rubrique pour découvrir comment procéder pour vérifier si vous disposez d’une licence en volume de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="05d4c-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="05d4c-105">Système de salle Skype utilise un Skype installé client d’entreprise, qui nécessite une licence en volume.</span><span class="sxs-lookup"><span data-stu-id="05d4c-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="05d4c-106">Avant de déployer le premier système de salle Skype, déterminer l’état de licence en volume du déploiement - à l’aide des serveurs de gestion de clés (KMS) ou clés d’Activation Multiple (MAK).</span><span class="sxs-lookup"><span data-stu-id="05d4c-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="05d4c-107">Serveurs de gestion de clés (KMS)</span><span class="sxs-lookup"><span data-stu-id="05d4c-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="05d4c-108">Si KMS est en place et distribuera Skype des activations de licence en Volume Business, le système de salle Skype activera automatiquement le Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="05d4c-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="05d4c-109">Pour savoir si vous disposez de KMS :</span><span class="sxs-lookup"><span data-stu-id="05d4c-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="05d4c-110">À partir d’une invite de commandes, exécutez :`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="05d4c-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="05d4c-111">Pour plus d’informations, voir [comment identifier les hôtes Office et Windows KMS via le DNS et supprimer des instances non autorisés](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="05d4c-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="05d4c-112">Pour configurer un KMS, voir [l’activation KMS d’Office 2013](https://technet.microsoft.com/library/ee624357.aspx) et [Gvlk pour l’activation KMS et Active Directory d’Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="05d4c-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="05d4c-113">Clé de licence en Volume Office 2013 générique pour Lync : 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (cette clé, le système de salle Skype rechercher un KMS sur le réseau.)</span><span class="sxs-lookup"><span data-stu-id="05d4c-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="05d4c-114">Clés d’activation multiple (MAK) à partir du Centre de service de licences en volume (VLSC)</span><span class="sxs-lookup"><span data-stu-id="05d4c-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="05d4c-115">Si le client utilise un autre logiciel avec une licence en volume, le service informatique gérera les activations de logiciel et le contrat de licence en volume (VLA) à l’aide du VLSC.</span><span class="sxs-lookup"><span data-stu-id="05d4c-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="05d4c-116">Cela permettra également la société à acheter Skype pour activations Business VL, après laquelle la société peut obtenir une clé MAK d’entrée dans la Console d’administration système Skype salle.</span><span class="sxs-lookup"><span data-stu-id="05d4c-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="05d4c-117">Un client disposant d’un VLA doit connaître ses informations d’identification VLSC, qui seront utilisées pour administrer le contrat et obtenir une MAK.</span><span class="sxs-lookup"><span data-stu-id="05d4c-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="05d4c-118">Si l’incertitude, finances du client doit être en mesure de confirmer si le client a payé une VLA.</span><span class="sxs-lookup"><span data-stu-id="05d4c-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="05d4c-119">Pour obtenir une MAK, accédez au Centre de service de licences en volume pour afficher les contrats et télécharger des clés de produit (MAK).</span><span class="sxs-lookup"><span data-stu-id="05d4c-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="05d4c-120">Pour plus d’informations, accédez au [Centre de gestion des licences en Volume](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="05d4c-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-office-365-without-vlsc-access"></a><span data-ttu-id="05d4c-121">MAK pour Office 365 sans accès au VLSC</span><span class="sxs-lookup"><span data-stu-id="05d4c-121">MAK for Office 365 without VLSC access</span></span>

<span data-ttu-id="05d4c-122">Si le client ne possède pas un contrat de licence en Volume, Skype pour activations Business sera beaucoup plus difficile à gérer.</span><span class="sxs-lookup"><span data-stu-id="05d4c-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="05d4c-123">Toutefois, les clients Office 365 sans accès de gestion des peuvent obtenir une clé MAK promotionnelle en fournissant les informations suivantes à l’OEM vente le système de salle de Skype :</span><span class="sxs-lookup"><span data-stu-id="05d4c-123">However, Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="05d4c-124">Nom de la société</span><span class="sxs-lookup"><span data-stu-id="05d4c-124">Company name</span></span>
    
- <span data-ttu-id="05d4c-125">Nom du contact pour le déploiement, e-mail et numéro de téléphone</span><span class="sxs-lookup"><span data-stu-id="05d4c-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="05d4c-126">Nombre de systèmes déployés</span><span class="sxs-lookup"><span data-stu-id="05d4c-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="05d4c-127">Date de déploiement</span><span class="sxs-lookup"><span data-stu-id="05d4c-127">Deployment date</span></span>
    
- <span data-ttu-id="05d4c-128">Si le client dispose d’un gestionnaire de comptes technique Microsoft, nom et les informations de contact de la gestion de comptes techniques</span><span class="sxs-lookup"><span data-stu-id="05d4c-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

