---
title: 'Lync Server 2013 : afficher la liste des applications approuvées'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 866286215389b0e446392bffe3e33f56a767f2e6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a>Afficher la liste des applications approuvées dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Vous pouvez utiliser le panneau de configuration Lync Server 2013 pour afficher la liste des applications approuvées que vous avez déployées dans votre environnement Lync Server 2013. Une application approuvée est une application basée sur Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK approuvé par Lync Server 2013. Cette relation d’approbation est résumée dans la liste suivante :

  - Les applications approuvées ne sont pas contestées pour l’authentification par Lync Server.

  - Les applications approuvées ne sont pas limitées par Lync Server pour les transactions SIP, les connexions ou les appels VoIP (Voice over Internet Protocol) sortants.

  - Les applications approuvées peuvent emprunter l’identité de n’importe quel utilisateur et participer à des conférences sans apparaître dans les listes.

  - Les applications approuvées sont hautement disponibles et résilientes.

Dans le panneau de configuration Lync Server, vous pouvez voir le nom des applications, le pool où elles s’exécutent, ainsi que le port qu’elles utilisent.

<div>

## <a name="to-view-a-list-of-trusted-applications"></a>Pour afficher la liste des applications approuvées

1.  Avec un compte d’utilisateur affecté au rôle CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne. Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Lync Server 2013, reportez-vous à la rubrique [Planning for Role-Based Access Control in Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **topologie** , puis sur **application approuvée**.

4.  Sur la page **application approuvée** , cliquez sur un en-tête de colonne pour trier les applications, le cas échéant.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Gestion de la topologie Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

