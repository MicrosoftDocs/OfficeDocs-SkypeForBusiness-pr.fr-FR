---
title: Skype espace système Skype pour la licence de logiciel d’entreprise
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Consultez cette rubrique pour découvrir comment procéder pour vérifier si vous disposez d’une licence en volume de Skype Entreprise.
ms.openlocfilehash: e91a009c29647031d91e791ba5fd41ccc4578d1e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="a53a0-103">Skype Room System : licence du logiciel Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="a53a0-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="a53a0-104">Consultez cette rubrique pour découvrir comment procéder pour vérifier si vous disposez d’une licence en volume de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="a53a0-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="a53a0-105">Système de chambre de Skype utilise un installé Skype pour client d’entreprise, qui nécessite une licence logicielle en volume.</span><span class="sxs-lookup"><span data-stu-id="a53a0-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="a53a0-106">Avant de déployer le premier système de salle Skype, déterminer l’état de licence de volume du déploiement - à l’aide de serveurs de gestion de clés (KMS) ou clés d’Activation Multiple (MAK).</span><span class="sxs-lookup"><span data-stu-id="a53a0-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="a53a0-107">Serveurs de gestion de clés (KMS)</span><span class="sxs-lookup"><span data-stu-id="a53a0-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="a53a0-108">Si KMS sont en place et distribuera Skype pour les activations de licence de Volume d’activité, le système de salle Skype activera automatiquement le Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a53a0-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="a53a0-109">Pour savoir si vous disposez de KMS :</span><span class="sxs-lookup"><span data-stu-id="a53a0-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="a53a0-110">À partir d’une invite de commande, exécutez :`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="a53a0-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="a53a0-111">Pour plus d’informations, consultez [comment identifier les hôtes KMS de Windows et de Office via DNS et de supprimer les instances non autorisées](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="a53a0-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="a53a0-112">Pour configurer un serveur gestionnaire de clés, consultez [activation KMS d’Office 2013](https://technet.microsoft.com/en-us/library/ee624357.aspx) et [GVLKs pour l’activation de KMS et Active Directory de Office 2013](https://technet.microsoft.com/en-us/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="a53a0-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/en-us/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/en-us/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="a53a0-113">Clé de licence en Volume Office 2013 générique pour Lync : 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (cette clé, le système de salle Skype rechercher un service KMS sur le réseau.)</span><span class="sxs-lookup"><span data-stu-id="a53a0-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="a53a0-114">Clés d’activation multiple (MAK) à partir du Centre de service de licences en volume (VLSC)</span><span class="sxs-lookup"><span data-stu-id="a53a0-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="a53a0-115">Si le client utilise un autre logiciel avec une licence en volume, le service informatique gérera les activations de logiciel et le contrat de licence en volume (VLA) à l’aide du VLSC.</span><span class="sxs-lookup"><span data-stu-id="a53a0-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="a53a0-116">Cela permettra également la société d’achat Skype pour les activations de Business VL, après laquelle la société peut obtenir une clé d’activation multiple pour l’entrée dans la Console d’administration système Skype salle.</span><span class="sxs-lookup"><span data-stu-id="a53a0-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="a53a0-117">Un client disposant d’un VLA doit connaître ses informations d’identification VLSC, qui seront utilisées pour administrer le contrat et obtenir une MAK.</span><span class="sxs-lookup"><span data-stu-id="a53a0-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="a53a0-118">Si elle est incertaine, département des finances du client doit être en mesure de confirmer si le client a payé une VLA.</span><span class="sxs-lookup"><span data-stu-id="a53a0-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="a53a0-119">Pour obtenir une MAK, accédez au Centre de service de licences en volume pour afficher les contrats et télécharger des clés de produit (MAK).</span><span class="sxs-lookup"><span data-stu-id="a53a0-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="a53a0-120">Pour plus d’informations, accédez au [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="a53a0-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-office-365-without-vlsc-access"></a><span data-ttu-id="a53a0-121">MAK pour Office 365 sans accès au VLSC</span><span class="sxs-lookup"><span data-stu-id="a53a0-121">MAK for Office 365 without VLSC access</span></span>

<span data-ttu-id="a53a0-122">Si le client ne possède pas un contrat de licence de Volume, Skype pour les activations de Business sera beaucoup plus difficile à gérer.</span><span class="sxs-lookup"><span data-stu-id="a53a0-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="a53a0-123">Les clients Office 365 sans accès à gestion des peuvent toutefois obtenir une MAK promotionnelle en fournissant les informations suivantes à l’OEM vendre le système de salle de Skype :</span><span class="sxs-lookup"><span data-stu-id="a53a0-123">However, Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="a53a0-124">Nom de la société</span><span class="sxs-lookup"><span data-stu-id="a53a0-124">Company name</span></span>
    
- <span data-ttu-id="a53a0-125">Nom du contact pour le déploiement, e-mail et numéro de téléphone</span><span class="sxs-lookup"><span data-stu-id="a53a0-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="a53a0-126">Nombre de systèmes déployés</span><span class="sxs-lookup"><span data-stu-id="a53a0-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="a53a0-127">Date de déploiement</span><span class="sxs-lookup"><span data-stu-id="a53a0-127">Deployment date</span></span>
    
- <span data-ttu-id="a53a0-128">Si le client possède un gestionnaire de compte technique Microsoft, nom et les coordonnées de la gestion de comptes techniques</span><span class="sxs-lookup"><span data-stu-id="a53a0-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

