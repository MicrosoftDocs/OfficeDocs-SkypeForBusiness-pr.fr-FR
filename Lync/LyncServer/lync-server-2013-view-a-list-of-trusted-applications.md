---
title: 'Lync Server 2013 : afficher une liste des applications approuvées'
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
ms.openlocfilehash: 3d5f9d112e045e753147f7fcffa875177a6feb0d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a>Afficher une liste des applications approuvées dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Vous pouvez utiliser le panneau de configuration de Lync Server 2013 pour afficher la liste des applications approuvées que vous avez déployées dans votre environnement Lync Server 2013. Une application fiable est une application basée sur le kit de développement logiciel (Unified Communications Managed API UCMA) 3,0 principal du SDK approuvé par Lync Server 2013. Cette relation d’approbation est résumée dans la liste suivante :

  - Les applications approuvées ne sont pas confrontées à l’authentification par Lync Server.

  - Les applications approuvées ne sont pas limitées par Lync Server pour les transactions SIP, les connexions ou les appels voix sur IP sortants.

  - Les applications approuvées peuvent emprunter l’identité d’un utilisateur et participer à des conférences sans apparaître dans les listes.

  - Les applications approuvées sont hautement disponibles et résilientes.

Dans le panneau de configuration de Lync Server, vous pouvez voir le nom de l’application, le pool sur lequel elle s’exécute et le port utilisé.

<div>

## <a name="to-view-a-list-of-trusted-applications"></a>Pour afficher une liste des applications approuvées

1.  À partir d’un compte d’utilisateur affecté au CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne. Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Lync Server 2013, voir [planification du contrôle d’accès basé sur les rôles dans Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Topology** et sur **application de confiance**.

4.  Dans la page **application fiable** , cliquez sur un en-tête de colonne pour trier les applications si nécessaire.

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

