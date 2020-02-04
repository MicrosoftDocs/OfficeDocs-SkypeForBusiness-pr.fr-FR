---
title: 'Lync Server 2013 : création ou modification des itinéraires de la région réseau'
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
ms.openlocfilehash: d877de116cc2cf3e0c3354bb6e53d69c211cb482
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a>Création ou modification des itinéraires de région réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-08_

Chaque région au sein d’une configuration de contrôle d’admission des appels (CAC) doit disposer d’un moyen d’accéder à toutes les autres régions. Lorsque les liaisons de zone définissent des limitations de bande passante pour les connexions entre les régions et représentent également les liens physiques, un itinéraire détermine le chemin d’accès lié que la connexion traverse d’une région à l’autre. Vous pouvez utiliser le panneau de configuration de Lync Server pour configurer les itinéraires de région réseau. Dans le panneau de configuration de Lync Server, vous pouvez créer, modifier ou supprimer un itinéraire de la région du réseau. Utilisez cette rubrique pour créer ou modifier un itinéraire de la région du réseau. Pour plus d’informations sur la suppression d’un itinéraire de région réseau existant, voir [Suppression d’itinéraires de région réseau existants dans Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).

<div>

## <a name="to-create-a-network-region-route"></a>Pour créer un itinéraire de la région du réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **itinéraire des régions**.

4.  Sur la page itinéraire de la **région** , cliquez sur **nouveau**.

5.  Dans la **zone nouvel itinéraire**de la région, tapez une valeur dans le champ **nom** .
    
    <div>
    

    > [!NOTE]  
    > Cette valeur doit être unique dans le cadre de votre déploiement de Microsoft Lync Server 2013.

    
    </div>

6.  Dans la liste déroulante ** \#région de réseau 1** , sélectionnez l’une des deux régions auxquelles vous voulez être connectée par cet itinéraire.

7.  Dans la liste déroulante de la ** \#région réseau 2** , sélectionnez une autre région pour ce routage. Cette région doit être différente de la région sélectionnée pour la région \#réseau 1.

8.  Utilisez la zone de liste **liaisons de région réseau** pour ajouter des liens de région à l’itinéraire. Cliquez sur le bouton **Ajouter** pour afficher la page de liaison de la **zone** . Cliquez sur le lien d’une région pour l’ajouter à ce routage, puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Continuez à cliquer sur le bouton <STRONG>Ajouter</STRONG> pour ajouter d’autres liens, ou sélectionnez un lien et cliquez sur <STRONG>supprimer</STRONG> pour supprimer un lien.

    
    </div>

9.  Cliquez sur **Valider**.

</div>

<div>

## <a name="to-modify-a-network-region-route"></a>Pour modifier un itinéraire de la région du réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **itinéraire des régions**.

4.  Sur la page itinéraire de la **région** , cliquez sur le secteur que vous voulez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la **zone modifier le routage**des régions, vous pouvez modifier les régions jointes par cet itinéraire et les liaisons de région associées à l’itinéraire.

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Supprimer des itinéraires de région réseau existants dans Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

