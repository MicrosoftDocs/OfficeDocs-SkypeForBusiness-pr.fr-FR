---
title: 'Lync Server 2013 : affichage et analyse des rapports de serveur de surveillance'
description: 'Lync Server 2013 : affichage et analyse des rapports de serveur de surveillance.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f2a1812d76a49d487bea35acae3e22ea403f105
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580040"
---
# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a>Affichage et analyse des rapports de serveur de surveillance dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-19_

Monitoring Server Reports propose différentes mesures de qualité des communications vocales pour surveiller le QoE qui est remis aux utilisateurs finaux. De plus, le serveur de surveillance comprend plusieurs rapports intégrés que votre organisation peut utiliser pour surveiller les tendances d’utilisation et de la qualité des médias sur le réseau de votre organisation et résoudre les problèmes de qualité des médias qui surviennent.

Une partie essentielle de la conservation des rapports de serveur de surveillance intéressants pour les opérations quotidiennes et hebdomadaires consiste à visualiser et à analyser des rapports sur la qualité des médias, en particulier :

  - Rapports de tendance/Résumé QoE

  - Rapports de performances QoE

<div>

## <a name="view-reports-from-the-monitoring-server"></a>Afficher les rapports du serveur de surveillance

1.  À partir d’un navigateur Web, Localisez vos serveurs hébergeant SQL Reporting Services.

2.  Affichez les rapports requis à partir de l’écran du navigateur.

3.  Module Exporter un rapport en sélectionnant l’option Exporter et le format de sortie requis.

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a>Configurer l’enregistrement des détails des appels

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant d’autorisations équivalentes), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Enregistrement des détails des appels**.

4.  Dans la page **Enregistrement des détails des appels**, cliquez sur le site approprié dans le tableau, cliquez sur **Modifier**, puis sur **Afficher les détails**.

5.  Pour activer le vidage, sélectionnez **activer le vidage pour les serveurs de surveillance**.

6.  Dans **conserver les enregistrements des détails des appels pendant la durée maximale (jours) :** sélectionnez le nombre maximal de jours pendant lesquels les enregistrements des détails des appels doivent être conservés.

7.  Dans **Conserver les données de signalement d’erreurs pendant la durée maximale (jours) :**, sélectionnez le nombre maximum de jours pendant lesquels les rapports d’erreurs sont à conserver.

8.  Cliquez sur **Valider**.

</div>

<div>

## <a name="configure-qoe"></a>Configurer QoE

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus de détails, voir Déléguer des autorisations de configuration.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.

4.  A la page **Données de qualité de l’expérience**, cliquez sur le site approprié dans le tableau, sur **Modifier**, puis sur **Afficher les détails**.

5.  Pour activer le vidage, sélectionnez **activer le vidage pour les serveurs de surveillance**.

6.  Dans **conserver les enregistrements des détails des appels pendant la durée maximale (jours) :** sélectionnez le nombre maximal de jours pendant lesquels les données QoE doivent être conservées.

7.  Cliquez sur Valider.

</div>

<div>

## <a name="change-the-archiving-policy"></a>Modifier la stratégie d’archivage

1.  À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.

4.  Cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la stratégie d’archivage - Globale**, procédez comme suit :

6.  Pour activer ou désactiver l’archivage interne pour le déploiement, activez ou désactivez la case à cocher **archiver les communications internes** .

7.  Pour activer ou désactiver l’archivage externe pour le déploiement, activez ou désactivez la case à cocher **archiver les communications externes** .

8.  Cliquez sur **Valider**.

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a>Appliquer une stratégie d’archivage à un utilisateur

1.  À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **modifier l’utilisateur Lync Server** , sous **stratégie d’archivage**, sélectionnez la stratégie utilisateur d’archivage que vous souhaitez appliquer.

6.  Cliquez sur **Valider**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Utilisation des rapports de surveillance dans Lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
[Rapport de performances du serveur dans Lync Server 2013](lync-server-2013-server-performance-report.md)  
[Rapport de comparaison de la qualité des médias dans Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

