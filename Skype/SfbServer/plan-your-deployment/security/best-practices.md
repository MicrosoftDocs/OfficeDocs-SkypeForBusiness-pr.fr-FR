---
title: Meilleures pratiques pour votre infrastructure principale dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Vous avez probablement déjà pris des mesures afin d’intégrer la tolérance de panne dans votre système, en utilisant diverses pratiques courantes telles que la mise en place d’une redondance au niveau du matériel, la protection contre les coupures de courant, l’installation régulière de mises à jour de sécurité, l’utilisation d’antivirus et le contrôle de l’activité du serveur. Ces pratiques profitent non seulement à votre infrastructure Skype Entreprise Server, mais également à l’ensemble de votre réseau. Si vous n’avez pas implémenté ces pratiques, nous vous recommandons de le faire avant de déployer Skype Entreprise Server.
ms.openlocfilehash: f2e9e019c5aadab57dddc8d8dcbb1b9090a160f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832244"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a><span data-ttu-id="3b9ff-105">Meilleures pratiques pour votre infrastructure principale dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="3b9ff-105">Best practices for your core infrastructure in Skype for Business Server</span></span>
 
<span data-ttu-id="3b9ff-106">Vous avez probablement déjà pris des mesures afin d’intégrer la tolérance de panne dans votre système, en utilisant diverses pratiques courantes telles que la mise en place d’une redondance au niveau du matériel, la protection contre les coupures de courant, l’installation régulière de mises à jour de sécurité, l’utilisation d’antivirus et le contrôle de l’activité du serveur.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-106">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="3b9ff-107">Ces pratiques profitent non seulement à votre infrastructure Skype Entreprise Server, mais également à l’ensemble de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-107">These practices benefit not only your Skype for Business Server infrastructure, but also your entire network.</span></span> <span data-ttu-id="3b9ff-108">Si vous n’avez pas implémenté ces pratiques, nous vous recommandons de le faire avant de déployer Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-108">If you have not implemented these practices, we recommend that you do so before deploying Skype for Business Server.</span></span>
  
<span data-ttu-id="3b9ff-109">Pour protéger les serveurs de votre déploiement Skype Entreprise Server contre les dommages accidentels ou intentionnables qui peuvent entraîner un temps d’arrêt, prenez les précautions suivantes :</span><span class="sxs-lookup"><span data-stu-id="3b9ff-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>
  
- <span data-ttu-id="3b9ff-110">Mettez régulièrement à jour vos serveurs en installant les mises à jour de sécurité.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-110">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="3b9ff-111">La souscription d’un abonnement au service de notification de sécurité de Microsoft permet de recevoir une notification immédiate des mises à jour de sécurité pour un produit Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-111">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="3b9ff-112">Pour vous abonner, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span><span class="sxs-lookup"><span data-stu-id="3b9ff-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span></span>
    
- <span data-ttu-id="3b9ff-113">Vérifiez que les droits d’accès sont correctement configurés.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-113">Ensure that access rights are set up correctly.</span></span>
    
- <span data-ttu-id="3b9ff-p104">Installez vos serveurs dans un environnement physique protégé contre les accès non autorisés. Vérifiez que les logiciels antivirus appropriés sont installés sur tous vos serveurs. Mettez à jour ces logiciels à l’aide des fichiers de signatures de virus les plus récents. Utilisez la fonction de mise à jour automatique de vos logiciels antivirus pour mettre à jour vos signatures de virus.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-p104">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>
    
- <span data-ttu-id="3b9ff-118">Nous vous recommandons de désactiver les services de système d’exploitation Windows Server qui ne sont pas requis sur les ordinateurs où vous installez Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-118">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Skype for Business Server.</span></span>
    
- <span data-ttu-id="3b9ff-119">Chiffrez les systèmes d’exploitation et les lecteurs de disques où les données sont stockées avec un système de chiffrement de volume complet, à moins que vous puissiez garantir un contrôle constant et total des serveurs, un isolement physique total, ainsi qu’une désaffectation en bonne et due forme des disques remplacés ou en échec.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-119">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>
    
- <span data-ttu-id="3b9ff-120">Désactivez tous les ports DMA (Direct Memory Access) externes du serveur, sauf si vous pouvez garantir un contrôle très serré de l’accès aux serveurs.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-120">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="3b9ff-121">Les attaques basées sur DMA, qui peuvent être initiées assez facilement, peuvent exposer des informations très sensibles, telles que des clés de chiffrement privées.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-121">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>
    

