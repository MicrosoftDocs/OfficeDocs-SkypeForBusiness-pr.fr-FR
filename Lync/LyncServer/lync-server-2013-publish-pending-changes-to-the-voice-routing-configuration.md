---
title: 'Lync Server 2013 : publication des modifications en attente de la configuration du routage des communications vocales'
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
ms.openlocfilehash: 86444047759c2eab605d8791a6445329651ad43f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a>Publier les modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-08-07_

Après avoir modifié les paramètres de configuration dans les pages du groupe **Routage des communications vocales**, effectuez cette procédure pour passer en revue, publier ou annuler les modifications en attente.

<div>


> [!IMPORTANT]  
> Vérifiez qu’un seul utilisateur à la fois modifie les paramètres de configuration du routage des communications vocales.<BR>Toutes les modifications en attente doivent être publiées en même temps en exécutant la commande <STRONG>Valider tout</STRONG>. Vous ne pouvez pas sélectionner les modifications en attente que vous voulez publier. Avant de publier les modifications en attente, exécutez la commande <STRONG>Vérifier les modifications non validées</STRONG> et annulez les modifications de configuration que vous ne voulez pas publier.<BR>Si vous quittez les pages du groupe <STRONG>Routage des communications vocales</STRONG> avant d’avoir validé les modifications en attente, toutes les modifications en attente seront perdues. Toutefois, vous pouvez exporter la configuration en cours (y compris les modifications en attente) vers un fichier de configuration des communications vocales, puis importer et publier la configuration mise à jour. Pour plus d’informations, consultez <A href="lync-server-2013-export-a-voice-route-configuration-file.md">la rubrique Exporter un fichier de configuration de routage des communications vocales dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>Pour passer en revue, publier ou annuler les modifications de la configuration du routage des communications vocales

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.

4.  Effectuez les modifications souhaitées au niveau de la configuration sur chacune des pages du groupe **Routage des communications vocales**.

5.  Pour passer en revue les modifications en attente sans les publier, sélectionnez **Vérifier les modifications non validées **dans le menu **Valider**.

6.  Si vous souhaitez annuler l’une des modifications en attente, effectuez l’une des opérations suivantes :
    
      - Sélectionnez **Annuler toutes les modifications non validées** dans le menu **Valider**.
    
      - Accédez à l’onglet de la page **Routage des communications vocales** où se trouvent les modifications en attente que vous souhaitez annuler, cliquez sur **Valider**, puis sur **Annuler les modifications sélectionnées**.

7.  Une fois que vous avez passé en revue toutes les modifications en attente et annulé celles que vous ne souhaitez pas publier, cliquez sur **Valider**, puis sur **Valider tout**.

8.  Dans la boîte de dialogue **Paramètres de configuration de la voix non validés** qui affiche la liste de toutes les modifications en attente, cliquez sur **OK**.
    
    Lorsque le panneau de configuration Lync Server a validé les modifications, le message la publication de la **configuration du routage des communications vocales a réussi** s’affiche.

</div>

</div>

<span> </span>

</div>

</div>

</div>

