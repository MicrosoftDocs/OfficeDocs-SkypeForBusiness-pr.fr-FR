---
title: 'Lync Server 2013 : meilleures pratiques pour votre infrastructure principale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 876a4de1357786e2d5089fdc632002107a6c7cc2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="3d5e3-102">Meilleures pratiques pour votre infrastructure de base dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d5e3-102">Best practices for your core infrastructure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d5e3-103">_**Dernière modification de la rubrique :** 2014-01-27_</span><span class="sxs-lookup"><span data-stu-id="3d5e3-103">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="3d5e3-104">Vous avez probablement déjà pris des mesures afin d’intégrer la tolérance de panne dans votre système, en utilisant diverses pratiques courantes telles que la mise en place d’une redondance au niveau du matériel, la protection contre les coupures de courant, l’installation régulière de mises à jour de sécurité, l’utilisation d’antivirus et le contrôle de l’activité du serveur.</span><span class="sxs-lookup"><span data-stu-id="3d5e3-104">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="3d5e3-105">Ces pratiques n’en bénéficient pas seulement de votre infrastructure Microsoft Lync Server 2013, mais aussi de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="3d5e3-105">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="3d5e3-106">Si vous n’avez pas implémenté ces pratiques, nous vous recommandons de le faire avant de déployer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d5e3-106">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="3d5e3-107">Pour protéger les serveurs de votre déploiement Lync Server 2013 contre les dommages accidentels ou involontaires susceptibles d’entraîner un temps d’arrêt, prenez les précautions suivantes :</span><span class="sxs-lookup"><span data-stu-id="3d5e3-107">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="3d5e3-108">Mettez régulièrement à jour vos serveurs en installant les mises à jour de sécurité.</span><span class="sxs-lookup"><span data-stu-id="3d5e3-108">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="3d5e3-109">La souscription d’un abonnement au service de notification de sécurité de Microsoft permet de recevoir une notification immédiate des mises à jour de sécurité pour un produit Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d5e3-109">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="3d5e3-110">Pour vous abonner, rendez-vous sur le site [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202)Web des notifications de sécurité technique Microsoft à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="3d5e3-110">To subscribe, go to the Microsoft Technical Security Notifications website at [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="3d5e3-111">Vérifiez que les droits d’accès sont correctement configurés.</span><span class="sxs-lookup"><span data-stu-id="3d5e3-111">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="3d5e3-p103">Installez vos serveurs dans un environnement physique protégé contre les accès non autorisés. Vérifiez que les logiciels antivirus appropriés sont installés sur tous vos serveurs. Mettez à jour ces logiciels à l’aide des fichiers de signatures de virus les plus récents. Utilisez la fonction de mise à jour automatique de vos logiciels antivirus pour mettre à jour vos signatures de virus.</span><span class="sxs-lookup"><span data-stu-id="3d5e3-p103">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="3d5e3-116">Nous vous recommandons de désactiver les services du système d’exploitation Windows Server qui ne sont pas nécessaires sur les ordinateurs sur lesquels vous installez Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d5e3-116">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="3d5e3-117">Chiffrez les systèmes d’exploitation et les lecteurs de disques où les données sont stockées avec un système de chiffrement de volume complet, à moins que vous puissiez garantir un contrôle constant et total des serveurs, un isolement physique total, ainsi qu’une désaffectation en bonne et due forme des disques remplacés ou en échec.</span><span class="sxs-lookup"><span data-stu-id="3d5e3-117">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="3d5e3-118">Désactivez tous les ports DMA (Direct Memory Access) externes du serveur, sauf si vous pouvez garantir un contrôle très serré de l’accès aux serveurs.</span><span class="sxs-lookup"><span data-stu-id="3d5e3-118">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="3d5e3-119">Les attaques basées sur DMA, qui peuvent être initiées assez facilement, peuvent exposer des informations très sensibles, telles que des clés de chiffrement privées.</span><span class="sxs-lookup"><span data-stu-id="3d5e3-119">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

