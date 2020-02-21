---
title: 'Lync Server 2013 : création ou modification des itinéraires de région réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32c5f3cdd8000892886b3273fbb33fc1b1f668e4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a>Création ou modification des itinéraires de région réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-08_

Chaque région au sein d’un contrôle d’admission des appels doit disposer d’un moyen lui permettant d’accéder à toutes les autres régions. Alors que les liens de région définissent des restrictions de bande passante sur les connexions entre les régions et qu’ils représentent également des liens physiques, un itinéraire détermine le chemin lié que la connexion traverse d’une région à une autre. Vous pouvez utiliser le panneau de configuration Lync Server pour configurer les itinéraires de région réseau. Dans le panneau de configuration Lync Server, vous pouvez créer, modifier ou supprimer un itinéraire de région réseau. Utilisez cette rubrique pour créer ou modifier un itinéraire de région réseau. Pour plus d’informations sur la suppression d’un itinéraire de région réseau existant, voir [Suppression de routes de région réseau existantes dans Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).

<div>

## <a name="to-create-a-network-region-route"></a>Pour créer un itinéraire de région réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Itinéraire de région**.

4.  Dans la page **Itinéraire de région**, cliquez sur **Nouveau**.

5.  Dans **Nouvel itinéraire de région**, tapez une valeur dans le champ **Nom**.
    
    <div>
    

    > [!NOTE]  
    > Cette valeur doit être unique dans votre déploiement de Microsoft Lync Server 2013.

    
    </div>

6.  Dans la liste déroulante ** \#région réseau 1** , sélectionnez l’une des deux régions à connecter par cet itinéraire.

7.  Dans la liste déroulante ** \#région réseau 2** , sélectionnez l’autre région pour cet itinéraire. Cette région doit être différente de la région sélectionnée pour la région \#réseau 1.

8.  Utilisez la zone de liste **Liens de région réseau** pour ajouter des liens de région à l’itinéraire. Cliquez sur le bouton **Ajouter** pour afficher la page **Lien de région**. Cliquez sur un lien de région pour l’ajouter à cet itinéraire, puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Continuez à cliquer sur le bouton <STRONG>Ajouter</STRONG> pour ajouter davantage de liens, ou sélectionnez un lien et cliquez sur <STRONG>Supprimer</STRONG> pour le supprimer.

    
    </div>

9.  Cliquez sur **Valider**.

</div>

<div>

## <a name="to-modify-a-network-region-route"></a>Pour modifier un itinéraire de région réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Itinéraire de région**.

4.  Dans la page **Itinéraire de région**, cliquez sur l’itinéraire de région que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans **Modifier l’itinéraire de région**, vous pouvez modifier les régions liées par cet itinéraire et les liens de région qui lui sont associés.

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Suppression des itinéraires de région réseau existants dans Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

