---
title: 'Lync Server 2013 : publier les modifications en attente apportées à la configuration de l’acheminement vocal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aac5c30cb73ef428d0571a1a0fe6853dbf70db4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a>Publier les modifications en attente apportées à la configuration du routage de la voix dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-08-07_

Après avoir modifié les paramètres de configuration dans les pages du groupe **Routage des communications vocales**, effectuez cette procédure pour consulter, publier ou annuler les modifications en attente.

<div>


> [!IMPORTANT]  
> Vérifiez qu’un seul utilisateur à la fois modifie les paramètres de configuration du routage des communications vocales.<BR>Toutes les modifications en attente doivent être publiées en même temps en exécutant la commande <STRONG>Tout valider</STRONG>. Vous ne pouvez pas sélectionner les modifications en attente que vous voulez publier. Avant de publier les modifications en attente, exécutez la commande <STRONG>Vérifier les modifications non validées</STRONG> et annulez les modifications de configuration que vous ne voulez pas publier.<BR>Si vous quittez les pages du groupe <STRONG>Routage des communications vocales</STRONG> avant d’avoir validé les modifications en attente, toutes les modifications en attente seront perdues. Cependant, vous pouvez exporter la configuration active (y compris les modifications en attente) vers un fichier de configuration des communications vocales, puis importer et publier la configuration mise à jour. Pour plus d’informations, voir <A href="lync-server-2013-export-a-voice-route-configuration-file.md">exporter un fichier de configuration de l’itinéraire vocal dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>Pour consulter, publier ou annuler les modifications de la configuration du routage des communications vocales

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.

4.  Effectuez les modifications souhaitées au niveau de la configuration dans chacune des pages du groupe **Routage des communications vocales**.

5.  Pour consulter les modifications en attente sans les publier, sélectionnez **Vérifier les modifications non validées** dans le menu **Valider**.

6.  Si vous souhaitez annuler l’une des modifications en attente, effectuez l’une des opérations suivantes :
    
      - Sélectionnez **Annuler toutes les modifications non validées** dans le menu **Valider**.
    
      - Accédez à l’onglet de la page **Routage des communications vocales** qui contient les modifications en attente que vous souhaitez annuler, cliquez sur **Valider**, puis sur **Annuler les modifications sélectionnées**.

7.  Une fois que vous avez vérifié toutes les modifications en attente et annulé celles que vous ne souhaitez pas publier, cliquez sur **Valider**, puis sur **Tout valider**.

8.  Dans la boîte de dialogue **Paramètres de configuration de la voix non validés** qui contient la liste de toutes les modifications en attente, cliquez sur **OK**.
    
    Lorsque le panneau de configuration de Lync Server a validé les modifications, le message **configuration de routage vocale correctement publié** s’affiche.

</div>

</div>

<span> </span>

</div>

</div>

</div>

