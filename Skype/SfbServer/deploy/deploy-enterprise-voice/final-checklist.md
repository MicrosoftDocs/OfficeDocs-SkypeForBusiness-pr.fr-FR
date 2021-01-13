---
title: Liste de vérification finale du déploiement du contrôle d’admission des appels pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Liste de vérification finale pour le déploiement du contrôle d’admission des appels (CAC) dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: d3a6484e35225627c8f22002823eff7fd5939694
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830834"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a><span data-ttu-id="74a6d-103">Déploiement du contrôle d’admission des appels : liste de vérification finale pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="74a6d-103">Call admission control deployment: final checklist for Skype for Business Server</span></span>
 
<span data-ttu-id="74a6d-104">Liste de vérification finale pour le déploiement du contrôle d’admission des appels (CAC) dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="74a6d-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="74a6d-105">Utilisez la liste de vérification suivante pour vérifier que vous avez effectué toutes les tâches de configuration nécessaires au déploiement du contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="74a6d-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="74a6d-p101">Si un ou plusieurs serveurs Edge sont déployés, chaque adresse IP de l’interface externe doit être ajoutée à la liste de sous-réseaux dans les paramètres de configuration réseau, avec un masque de 32 bits. Vous devez également associer ce sous-réseau (adresse IP) à l’ID de site réseau pour l’emplacement géographique où est déployé le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="74a6d-p101">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32. You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="74a6d-108">Les serveurs Edge ne sont pas requis pour implémenter le service Cac.</span><span class="sxs-lookup"><span data-stu-id="74a6d-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="74a6d-109">Assurez-vous que le contrôle d’admission des appels est activé, comme indiqué dans Activer le contrôle d’admission des [appels dans Skype Entreprise Server.](enable-call-admission-control.md)</span><span class="sxs-lookup"><span data-stu-id="74a6d-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="74a6d-110">Vérifiez que le contrôle d’admission des appels est activé sur tous les sites centraux.</span><span class="sxs-lookup"><span data-stu-id="74a6d-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="74a6d-111">Pour ce faire, vous pouvez utiliser le Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="74a6d-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="74a6d-112">Si un avertissement est généré lors de la publication,  *ne l’ignorez*  pas.</span><span class="sxs-lookup"><span data-stu-id="74a6d-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="74a6d-113">Vérifiez que tous les sous-réseaux qui sont gérés dans le réseau d’entreprise sont configurés dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="74a6d-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="74a6d-114">Il est également essentiel que chaque sous-réseau soit associé à un site réseau, comme expliqué dans Déployer des régions réseau, des sites et des sous-réseaux [dans Skype Entreprise.](deploy-network.md)</span><span class="sxs-lookup"><span data-stu-id="74a6d-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
- <span data-ttu-id="74a6d-115">Vérifiez que les adresses IP ou de sous-réseau de tous les serveurs frontaux, SBA (Survivable Branch Appliances), serveurs de conférence Audio/Vidéo (s’ils figurent dans un pool distinct) et serveurs de médiation sont configurées dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="74a6d-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

