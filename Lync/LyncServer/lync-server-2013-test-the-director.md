---
title: 'Lync Server 2013 : Test du directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b82b8b7e494a66cf38fd27e37f322c79e95f801c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a>Test du directeur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

À ce stade, un directeur ou un pool de réalisateur est configuré, mais les entrées SRV de votre système de noms de domaine (DNS) continuent à se connecter à l’aide d’un pool ou d’un serveur Standard Edition Server. Avant de modifier l’enregistrement DNS pour que les clients Lync 2013 se connectent automatiquement à l’aide du réalisateur, testez un client en le faisant manuellement au directeur.

<div>

## <a name="to-test-the-deployment"></a>Pour tester le déploiement

1.  Ouvrez une session sur l’ordinateur sur lequel est installé le panneau de configuration de Lync Server avec un compte de domaine faisant partie du groupe **CSAdministrator** .

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans le volet de navigation, cliquez sur **Topology**, puis, dans la colonne **statut** , vérifiez qu’il existe un serveur vert avec une flèche (c’est-à-dire, l' ![icône du serveur avec la flèche verte](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Icône serveur avec flèche verte")) pour votre directeur ou votre pool de réalisateur.

4.  Connectez deux ordinateurs client sur lesquels le client Lync Server 2013 est installé, puis connectez-vous avec un autre compte d’utilisateur activé pour Lync Server 2013 sur chaque ordinateur.

5.  Sur l’un des ordinateurs clients, cliquez sur le menu **options** , sélectionnez le groupe paramètres **personnels** , cliquez sur **avancé**, sur **configuration manuelle**, puis définissez le **nom du serveur interne ou l’adresse IP** sur le nom de domaine complet (FQDN) du nouveau directeur ou du pool de réalisateurs.

6.  Ouvrez une session sur les deux clients et assurez-vous que le client qui se connecte à l’aide du directeur est en mesure de se connecter avec succès, d’afficher le statut de présence de l’autre utilisateur et de pouvoir échanger des messages instantanés.

</div>

</div>

<span> </span>

</div>

</div>

</div>

