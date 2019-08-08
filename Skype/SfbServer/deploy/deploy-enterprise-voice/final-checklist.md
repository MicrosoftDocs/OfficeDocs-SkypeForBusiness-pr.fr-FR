---
title: Liste de vérification de déploiement des contrôles d’admission des appels pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Liste de vérification finale pour le déploiement du contrôle d’admission des appels (CAC) dans Skype entreprise Server Voice.
ms.openlocfilehash: 275afdfcb3c5e2b7cc635e073bcb5b9ba5edc853
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240316"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a><span data-ttu-id="40087-103">Déploiement du contrôle d’admission des appels: liste de vérification finale pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="40087-103">Call admission control deployment: final checklist for Skype for Business Server</span></span>
 
<span data-ttu-id="40087-104">Liste de vérification finale pour le déploiement du contrôle d’admission des appels (CAC) dans Skype entreprise Server Voice.</span><span class="sxs-lookup"><span data-stu-id="40087-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="40087-105">Servez-vous de la liste de contrôle suivante pour vérifier que vous avez exécuté toutes les tâches de configuration nécessaires au déploiement du contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="40087-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="40087-106">Si au moins un serveur Edge est déployé, chaque adresse IP de l’interface externe doit être ajoutée à la liste des sous-réseaux dans les paramètres de configuration du réseau, avec un masque de bits de 32.</span><span class="sxs-lookup"><span data-stu-id="40087-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="40087-107">Vous devez également associer ce sous-réseau (adresse IP) à l’ID de site réseau pour l’emplacement géographique auquel le service Edge A/V est déployé.</span><span class="sxs-lookup"><span data-stu-id="40087-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40087-108">Il n’est pas nécessaire de mettre en place des serveurs de périphérie pour le CAC.</span><span class="sxs-lookup"><span data-stu-id="40087-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="40087-109">Assurez-vous que le contrôle CAC est activé, tel qu’il est spécifié dans [activer le contrôle d’admission des appels dans Skype entreprise Server](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="40087-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="40087-110">Vérifiez que le contrôle d’admission des appels est activé sur tous les sites centraux.</span><span class="sxs-lookup"><span data-stu-id="40087-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="40087-111">Cette opération peut être réalisée par le biais du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="40087-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="40087-112">Si un message d’avertissement est généré lors de la publication, ne l’ignorez *pas* .</span><span class="sxs-lookup"><span data-stu-id="40087-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="40087-113">Vérifiez que tous les sous-réseaux gérés dans le réseau d’entreprise sont configurés dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="40087-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="40087-114">Il est également essentiel que chaque sous-réseau soit associé à un site réseau, comme décrit dans la rubrique [déploiement de régions réseau, de sites et de sous-réseaux dans Skype entreprise](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="40087-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
- <span data-ttu-id="40087-115">Vérifiez que les adresses IP ou de sous-réseau de tous les serveurs frontaux, SBA (Survivable Branch Appliances), serveurs de conférence audio/vidéo (s’ils figurent dans un pool distinct) et serveurs de médiation sont configurées dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="40087-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

