---
title: 'Lync Server 2013: meilleures pratiques pour votre infrastructure principale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfb6e12f6f2c6d66a0d4f5fed17bc01dc250db5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="cd6b1-102">Recommandations en matière d’infrastructure de base dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd6b1-102">Best practices for your core infrastructure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd6b1-103">_**Dernière modification de la rubrique:** 2014-01-27_</span><span class="sxs-lookup"><span data-stu-id="cd6b1-103">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="cd6b1-104">Vous avez probablement déjà pris des mesures pour intégrer la tolérance de pannes dans votre système, en utilisant des pratiques telles que la garantie de la redondance matérielle, la prévention de la perte d'alimentation, l'installation régulière des mises à jour, l'établissement des mesures de sécurité antivirus et la surveillance de l'activité du serveur.</span><span class="sxs-lookup"><span data-stu-id="cd6b1-104">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="cd6b1-105">Ces pratiques profitent non seulement de votre infrastructure Microsoft Lync Server 2013, mais aussi de votre réseau entier.</span><span class="sxs-lookup"><span data-stu-id="cd6b1-105">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="cd6b1-106">Si vous n’avez pas implémenté ces pratiques, nous vous conseillons de le faire avant de déployer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cd6b1-106">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="cd6b1-107">Pour vous aider à protéger les serveurs dans votre déploiement de Lync Server 2013 contre les dommages accidentels ou intentionnelles susceptibles d’entraîner un temps d’arrêt, prenez les précautions suivantes:</span><span class="sxs-lookup"><span data-stu-id="cd6b1-107">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="cd6b1-108">Maintenez vos serveurs à jour avec les mises à jour de sécurité.</span><span class="sxs-lookup"><span data-stu-id="cd6b1-108">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="cd6b1-109">En vous abonnant au service de notification de sécurité de Microsoft, vous recevez la notification immédiate des bulletins de sécurité pour les produits Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cd6b1-109">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="cd6b1-110">Pour vous abonner, accédez au site Web Microsoft Technical Security [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)notifications à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="cd6b1-110">To subscribe, go to the Microsoft Technical Security Notifications website at [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="cd6b1-111">Assurez-vous que les droits d'accès sont configurés correctement.</span><span class="sxs-lookup"><span data-stu-id="cd6b1-111">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="cd6b1-p103">Conservez vos serveurs dans un environnement physique qui empêche l'accès non autorisé. Assurez-vous que le logiciel antivirus adéquat est installé sur tous vos serveurs. Maintenez le logiciel à jour avec les derniers fichiers de signatures de virus. Utilisez la fonction de mise à jour automatique de votre application antivirus pour maintenir à jour les signatures de virus.</span><span class="sxs-lookup"><span data-stu-id="cd6b1-p103">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="cd6b1-116">Nous vous recommandons de désactiver les services du système d’exploitation Windows Server qui ne sont pas nécessaires sur les ordinateurs sur lesquels vous installez Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cd6b1-116">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="cd6b1-117">Chiffrez les systèmes d'exploitation et les lecteurs de disques où les données sont stockées à l'aide d'un système de chiffrement de volume complet, sauf si vous pouvez garantir un contrôle constant et total des serveurs, l'isolement physique complet et la désaffectation adéquate et sûre des disques remplacés ou défaillants.</span><span class="sxs-lookup"><span data-stu-id="cd6b1-117">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="cd6b1-118">Désactivez tous les ports DMA (Direct Memory Access) externes du serveur, sauf si vous pouvez garantir un contrôle très strict de l'accès physique aux serveurs.</span><span class="sxs-lookup"><span data-stu-id="cd6b1-118">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="cd6b1-119">Les attaques basées sur DMA, qui peuvent être lancées assez facilement, risquent d'exposer des informations très sensibles, telles que les clés de chiffrement privées.</span><span class="sxs-lookup"><span data-stu-id="cd6b1-119">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

