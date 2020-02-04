---
title: 'Lync Server 2013 : affichage et analyse des rapports du serveur de surveillance'
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
ms.openlocfilehash: 9e4fce6cf17601d2a68a07a3b832e6b50c10b759
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a>Affichage et analyse des rapports du serveur de surveillance dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-19_

Le rapport analyse du serveur fournit différentes mesures de qualité de la voix pour contrôler le QoE qui est remis aux utilisateurs finaux. Par ailleurs, la surveillance du serveur comporte plusieurs rapports prédéfinis que votre organisation peut utiliser pour surveiller les tendances d’utilisation et de qualité multimédia sur le réseau de votre organisation et résoudre les problèmes de qualité de média.

Un élément principal de la conservation des rapports du serveur de surveillance intéressants pour les opérations quotidiennes et hebdomadaires consiste à afficher et à analyser des rapports de qualité multimédia, en particulier :

  - Rapport de synthèse

  - Rapports sur les performances QoE

<div>

## <a name="view-reports-from-the-monitoring-server"></a>Afficher des rapports du serveur de surveillance

1.  Dans un navigateur Web, recherchez les serveurs hébergeant SQL Reporting Services.

2.  Affichez les rapports nécessaires à partir de l’écran du navigateur.

3.  Facultatif Exportez un rapport en sélectionnant l’option Exporter et le format de sortie requis.

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a>Configurer l’enregistrement des détails des appels (CDR)

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté d’autorisations équivalentes) ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Enregistrement des détails des appels**.

4.  Dans la page **Enregistrement des détails des appels**, cliquez sur le site approprié dans le tableau, cliquez sur **Modifier**, puis sur **Afficher les détails**.

5.  Pour activer le vidage, sélectionnez **activer la purge pour la surveillance des serveurs**.

6.  Dans **conserver les enregistrements des détails des appels pour une durée maximale (jours) :** sélectionnez le nombre maximal de jours pendant lequel les enregistrements des détails des appels doivent être conservés.

7.  Dans **Conserver les données de signalement d’erreurs pendant la durée maximale (jours) :**, sélectionnez le nombre maximum de jours pendant lesquels les rapports d’erreurs sont à conserver.

8.  Cliquez sur **Valider**.

</div>

<div>

## <a name="configure-qoe"></a>Configurer QoE

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez autorisations de configuration de délégué.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.

4.  Dans la page **Données de qualité de l’expérience**, cliquez sur le site approprié dans le tableau, sur **Modifier**, puis sur **Afficher les détails**.

5.  Pour activer le vidage, sélectionnez **activer la purge pour la surveillance des serveurs**.

6.  Dans **conserver les enregistrements des détails des appels pour une durée maximale (jours) :** sélectionnez le nombre maximal de jours pendant lequel les données QoE doivent être conservées.

7.  Cliquez sur Valider.

</div>

<div>

## <a name="change-the-archiving-policy"></a>Modifier la stratégie d’archivage

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.

3.  Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **stratégie d’archivage**.

4.  Cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la stratégie d’archivage - Globale**, procédez comme suit :

6.  Pour activer ou désactiver l’archivage interne pour le déploiement, cochez ou décochez la case **archiver les communications internes** .

7.  Pour activer ou désactiver l’archivage externe pour le déploiement, cochez ou décochez la case **archiver les communications externes** .

8.  Cliquez sur **Valider**.

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a>Appliquer une stratégie d’archivage à un utilisateur

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur à configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **modifier l’utilisateur de Lync Server** sous **stratégie d’archivage**, sélectionnez la stratégie d’utilisateur d’archivage que vous voulez appliquer.

6.  Cliquez sur **Valider**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Utilisation de rapports d’analyse dans Lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
[Rapport sur les performances du serveur dans Lync Server 2013](lync-server-2013-server-performance-report.md)  
[Rapport de comparaison de qualité multimédia dans Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

