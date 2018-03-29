---
title: Appeler admission contrôle final du pré-déploiement pour Skype Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Liste de vérification finale pour le déploiement d’appeler contrôle d’Admission (CAC) dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 9971d59f0b9c3c2c1f9bfd5e8176122715b19d20
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server-2015"></a><span data-ttu-id="89b4d-103">Déploiement du contrôle d’admission des appels : liste de vérification finale pour Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="89b4d-103">Call admission control deployment: final checklist for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="89b4d-104">Liste de vérification finale pour le déploiement d’appeler contrôle d’Admission (CAC) dans Skype pour Business Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="89b4d-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="89b4d-105">Servez-vous de la liste de contrôle suivante pour vérifier que vous avez exécuté toutes les tâches de configuration nécessaires au déploiement du contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="89b4d-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="89b4d-106">Si un ou plusieurs serveurs Edge sont déployés, chaque adresse de l’interface externe doit être ajouté à la liste des sous-réseaux dans les paramètres de configuration réseau, avec un masque de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="89b4d-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="89b4d-107">Vous devez également associer ce sous-réseau (adresse IP) à l’ID de site réseau pour l’emplacement géographique auquel le service Edge A/V est déployé.</span><span class="sxs-lookup"><span data-stu-id="89b4d-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="89b4d-108">Les serveurs Edge n’êtes pas obligés de mettre en œuvre la CAC.</span><span class="sxs-lookup"><span data-stu-id="89b4d-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="89b4d-109">Assurez-vous que le CAC est activé, comme spécifié dans [le contrôle d’admission appel activer dans Skype pour Business Server 2015](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="89b4d-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server 2015](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="89b4d-110">Vérifiez que le contrôle d’admission des appels est activé sur tous les sites centraux.</span><span class="sxs-lookup"><span data-stu-id="89b4d-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="89b4d-111">Pour ce faire par le biais du Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="89b4d-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="89b4d-112">Si un avertissement est généré lors de la publication, *ne le faites pas* l’ignorer.</span><span class="sxs-lookup"><span data-stu-id="89b4d-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="89b4d-113">Vérifiez que tous les sous-réseaux gérés dans le réseau d’entreprise sont configurés dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="89b4d-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="89b4d-114">Il est également essentiel que chaque sous-réseau est associé à un site de réseau, comme expliqué dans les [régions de réseau, des sites et des sous-réseaux dans Skype pour entreprise 2015 déployer](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="89b4d-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business 2015](deploy-network.md).</span></span>
    
- <span data-ttu-id="89b4d-115">Vérifiez que les adresses IP ou de sous-réseau de tous les serveurs frontaux, SBA (Survivable Branch Appliances), serveurs de conférence audio/vidéo (s’ils figurent dans un pool distinct) et serveurs de médiation sont configurées dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="89b4d-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

