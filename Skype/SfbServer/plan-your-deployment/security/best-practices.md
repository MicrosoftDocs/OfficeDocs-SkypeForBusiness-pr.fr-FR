---
title: Meilleures pratiques pour votre infrastructure principale dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Vous avez probablement déjà pris des mesures pour intégrer la tolérance de pannes dans votre système, en utilisant des pratiques telles que la garantie de la redondance matérielle, la prévention de la perte d'alimentation, l'installation régulière des mises à jour, l'établissement des mesures de sécurité antivirus et la surveillance de l'activité du serveur. Ces pratiques sont bénéfiques non seulement votre Skype pour l’infrastructure de serveur d’entreprise, mais aussi tout votre réseau. Si vous n’avez pas implémenté ces pratiques, nous vous recommandons de le faire avant de déployer Skype pour Business Server.
ms.openlocfilehash: 86d18e1d9d34b5f65f4cb938e13a9829af1646bb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885805"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a><span data-ttu-id="09c0f-105">Meilleures pratiques pour votre infrastructure principale dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="09c0f-105">Best practices for your core infrastructure in Skype for Business Server</span></span>
 
<span data-ttu-id="09c0f-106">Vous avez probablement déjà pris des mesures pour intégrer la tolérance de pannes dans votre système, en utilisant des pratiques telles que la garantie de la redondance matérielle, la prévention de la perte d'alimentation, l'installation régulière des mises à jour, l'établissement des mesures de sécurité antivirus et la surveillance de l'activité du serveur.</span><span class="sxs-lookup"><span data-stu-id="09c0f-106">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="09c0f-107">Ces pratiques sont bénéfiques non seulement votre Skype pour l’infrastructure de serveur d’entreprise, mais aussi tout votre réseau.</span><span class="sxs-lookup"><span data-stu-id="09c0f-107">These practices benefit not only your Skype for Business Server infrastructure, but also your entire network.</span></span> <span data-ttu-id="09c0f-108">Si vous n’avez pas implémenté ces pratiques, nous vous recommandons de le faire avant de déployer Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="09c0f-108">If you have not implemented these practices, we recommend that you do so before deploying Skype for Business Server.</span></span>
  
<span data-ttu-id="09c0f-109">Pour protéger les serveurs de votre Skype pour le déploiement de serveur d’entreprise à partir de dommages accidentels ou intentionnelle pouvant entraîner des temps d’arrêt, prenez les précautions suivantes :</span><span class="sxs-lookup"><span data-stu-id="09c0f-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>
  
- <span data-ttu-id="09c0f-110">Maintenez vos serveurs à jour avec les mises à jour de sécurité.</span><span class="sxs-lookup"><span data-stu-id="09c0f-110">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="09c0f-111">En vous abonnant au service de notification de sécurité de Microsoft, vous recevez la notification immédiate des bulletins de sécurité pour les produits Microsoft.</span><span class="sxs-lookup"><span data-stu-id="09c0f-111">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="09c0f-112">Pour vous abonner, rendez-vous sur le [site Web du service de notification de sécurité de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span><span class="sxs-lookup"><span data-stu-id="09c0f-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span></span>
    
- <span data-ttu-id="09c0f-113">Assurez-vous que les droits d'accès sont configurés correctement.</span><span class="sxs-lookup"><span data-stu-id="09c0f-113">Ensure that access rights are set up correctly.</span></span>
    
- <span data-ttu-id="09c0f-p104">Conservez vos serveurs dans un environnement physique qui empêche l'accès non autorisé. Assurez-vous que le logiciel antivirus adéquat est installé sur tous vos serveurs. Maintenez le logiciel à jour avec les derniers fichiers de signatures de virus. Utilisez la fonction de mise à jour automatique de votre application antivirus pour maintenir à jour les signatures de virus.</span><span class="sxs-lookup"><span data-stu-id="09c0f-p104">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>
    
- <span data-ttu-id="09c0f-118">Nous vous recommandons de désactiver les services de système d’exploitation Windows Server qui ne sont pas indispensables sur les ordinateurs sur lesquels vous installez Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="09c0f-118">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Skype for Business Server.</span></span>
    
- <span data-ttu-id="09c0f-119">Chiffrez les systèmes d'exploitation et les lecteurs de disques où les données sont stockées à l'aide d'un système de chiffrement de volume complet, sauf si vous pouvez garantir un contrôle constant et total des serveurs, l'isolement physique complet et la désaffectation adéquate et sûre des disques remplacés ou défaillants.</span><span class="sxs-lookup"><span data-stu-id="09c0f-119">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>
    
- <span data-ttu-id="09c0f-120">Désactivez tous les ports DMA (Direct Memory Access) externes du serveur, sauf si vous pouvez garantir un contrôle très strict de l'accès physique aux serveurs.</span><span class="sxs-lookup"><span data-stu-id="09c0f-120">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="09c0f-121">Les attaques basées sur DMA, qui peuvent être lancées assez facilement, risquent d'exposer des informations très sensibles, telles que les clés de chiffrement privées.</span><span class="sxs-lookup"><span data-stu-id="09c0f-121">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>
    

