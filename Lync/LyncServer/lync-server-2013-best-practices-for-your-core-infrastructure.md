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
ms.openlocfilehash: cd53ac85ec544af58c1f94f7397a030f6b10fdb2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a>Meilleures pratiques pour votre infrastructure de base dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-01-27_

Vous avez probablement déjà pris des mesures afin d’intégrer la tolérance de panne dans votre système, en utilisant diverses pratiques courantes telles que la mise en place d’une redondance au niveau du matériel, la protection contre les coupures de courant, l’installation régulière de mises à jour de sécurité, l’utilisation d’antivirus et le contrôle de l’activité du serveur. Ces pratiques n’en bénéficient pas seulement de votre infrastructure Microsoft Lync Server 2013, mais aussi de votre réseau. Si vous n’avez pas implémenté ces pratiques, nous vous recommandons de le faire avant de déployer Lync Server 2013.

Pour protéger les serveurs de votre déploiement Lync Server 2013 contre les dommages accidentels ou involontaires susceptibles d’entraîner un temps d’arrêt, prenez les précautions suivantes :

  - Mettez régulièrement à jour vos serveurs en installant les mises à jour de sécurité. La souscription d’un abonnement au service de notification de sécurité de Microsoft permet de recevoir une notification immédiate des mises à jour de sécurité pour un produit Microsoft. Pour vous abonner, rendez-vous sur le site [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)Web des notifications de sécurité technique Microsoft à l’adresse.

  - Vérifiez que les droits d’accès sont correctement configurés.

  - Installez vos serveurs dans un environnement physique protégé contre les accès non autorisés. Vérifiez que les logiciels antivirus appropriés sont installés sur tous vos serveurs. Mettez à jour ces logiciels à l’aide des fichiers de signatures de virus les plus récents. Utilisez la fonction de mise à jour automatique de vos logiciels antivirus pour mettre à jour vos signatures de virus.

  - Nous vous recommandons de désactiver les services du système d’exploitation Windows Server qui ne sont pas nécessaires sur les ordinateurs sur lesquels vous installez Lync Server 2013.

  - Chiffrez les systèmes d’exploitation et les lecteurs de disques où les données sont stockées avec un système de chiffrement de volume complet, à moins que vous puissiez garantir un contrôle constant et total des serveurs, un isolement physique total, ainsi qu’une désaffectation en bonne et due forme des disques remplacés ou en échec.

  - Désactivez tous les ports DMA (Direct Memory Access) externes du serveur, sauf si vous pouvez garantir un contrôle très serré de l’accès aux serveurs. Les attaques basées sur DMA, qui peuvent être initiées assez facilement, peuvent exposer des informations très sensibles, telles que des clés de chiffrement privées.

</div>

<span> </span>

</div>

</div>

</div>

