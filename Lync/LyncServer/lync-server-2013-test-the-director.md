---
title: 'Lync Server 2013 : test du directeur'
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
ms.openlocfilehash: ad5c885e032800e4233aaa58c5238c066a87a1df
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a>Test du directeur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

À ce stade, vous avez un directeur ou un pool directeur configuré, mais vos entrées SRV DNS (Domain Name System) désignent toujours les clients pour se connecter à l’aide d’un pool ou d’un serveur Standard Edition. Avant de modifier l’enregistrement DNS pour faire en sorte que les clients Lync 2013 se connectent automatiquement à l’aide du directeur, testez un client en le dirigeant manuellement vers le directeur.

<div>

## <a name="to-test-the-deployment"></a>Pour tester le déploiement

1.  Ouvrez une session sur l’ordinateur sur lequel le panneau de configuration Lync Server est installé avec un compte de domaine qui fait partie du groupe **CSAdministrator** .

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans le volet de navigation, cliquez sur **topologie**, puis, dans la colonne **État** , vérifiez qu’il y a un serveur vert avec une flèche (c’est-à-dire, une ![icône de serveur avec flèche verte](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Icône de serveur avec flèche verte")) pour votre directeur ou pool directeur.

4.  Connectez deux ordinateurs clients sur lesquels le client Lync Server 2013 est installé, puis ouvrez une session avec un autre compte d’utilisateur activé pour Lync Server 2013 sur chaque ordinateur.

5.  Sur l’un des ordinateurs clients, cliquez sur le menu **options** , sélectionnez le groupe paramètres **personnels** , cliquez sur **avancé**, cliquez sur **configuration manuelle**, puis définissez le **nom du serveur interne ou l’adresse IP** sur le nom de domaine complet (FQDN) du nouveau directeur ou pool directeur.

6.  Ouvrez une session sur les deux clients et vérifiez que le client qui ouvre une session à l’aide du directeur est en mesure de se connecter correctement, de voir le statut de présence de l’autre utilisateur et de pouvoir échanger des messages instantanés.

</div>

</div>

<span> </span>

</div>

</div>

</div>

