---
title: Appeler liste finale du déploiement de contrôle d’admission des appels de Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Liste de vérification finale pour le déploiement d’admission des appels contrôle appels (CAC) dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 841a3a8d124a50142cd3644dd6f001e6019af9f3
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885475"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a><span data-ttu-id="278fb-103">Déploiement du contrôle d’admission des appels : liste de vérification finale pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="278fb-103">Call admission control deployment: final checklist for Skype for Business Server</span></span>
 
<span data-ttu-id="278fb-104">Liste de vérification finale pour le déploiement d’admission des appels contrôle appels (CAC) dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="278fb-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="278fb-105">Servez-vous de la liste de contrôle suivante pour vérifier que vous avez exécuté toutes les tâches de configuration nécessaires au déploiement du contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="278fb-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="278fb-106">Si un ou plusieurs serveurs Edge sont déployés, chaque adresse de l’interface externe doit être ajouté à la liste de sous-réseau dans les paramètres de configuration réseau, avec un masque de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="278fb-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="278fb-107">Vous devez également associer ce sous-réseau (adresse IP) à l’ID de site réseau pour l’emplacement géographique auquel le service Edge A/V est déployé.</span><span class="sxs-lookup"><span data-stu-id="278fb-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="278fb-108">Serveurs de périphérie ne sont pas tenus d’implémenter CAC.</span><span class="sxs-lookup"><span data-stu-id="278fb-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="278fb-109">Assurez-vous que CAC est activé, comme spécifié dans [le contrôle d’admission des appels d’appel activer dans Skype pour Business Server](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="278fb-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="278fb-110">Vérifiez que le contrôle d’admission des appels est activé sur tous les sites centraux.</span><span class="sxs-lookup"><span data-stu-id="278fb-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="278fb-111">Pour ce faire par le biais du Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="278fb-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="278fb-112">Si un avertissement est généré lorsque vous publiez, *ne mais pas* l’ignorer.</span><span class="sxs-lookup"><span data-stu-id="278fb-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="278fb-113">Vérifiez que tous les sous-réseaux gérés dans le réseau d’entreprise sont configurés dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="278fb-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="278fb-114">Il est également indispensable que tous les sous-réseaux associés à un site réseau, comme expliqué dans les [régions de réseau de déploiement, des sites et sous-réseaux de Skype pour les entreprises](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="278fb-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
- <span data-ttu-id="278fb-115">Vérifiez que les adresses IP ou de sous-réseau de tous les serveurs frontaux, SBA (Survivable Branch Appliances), serveurs de conférence audio/vidéo (s’ils figurent dans un pool distinct) et serveurs de médiation sont configurées dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="278fb-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

