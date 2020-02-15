---
title: 'Lync Server 2013 : création ou modification des fournisseurs fédérés SIP hébergés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68e87e5a6a59c2e14705d8a89578a0408c39b8e6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a>Créer ou modifier des fournisseurs fédérés SIP hébergés Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

La connectivité de messagerie instantanée des fournisseurs hébergés permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs des services de messagerie instantanée fournis par des fournisseurs hébergés, notamment Microsoft Office 365 et Lync Online.

Chaque fournisseur hébergé est configuré avec le nom de domaine complet du serveur Edge du fournisseur et le niveau de vérification par défaut **Autoriser les utilisateurs à communiquer avec les personnes dans leur liste des contacts qui utilisent ce fournisseur**.

Procédez comme suit pour créer ou modifier des fournisseurs hébergés :

<div>

## <a name="to-create-or-edit-hosted-providers"></a>Pour créer ou modifier des fournisseurs hébergés

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Fournisseurs fédérés SIP**.

4.  Si vous devez créer un nouveau fournisseur hébergé, cliquez sur **Nouveau**, puis sur **Fournisseur hébergé**.

5.  Si vous devez modifier une entrée dans la liste des fournisseurs hébergés, sélectionnez un fournisseur hébergé, cliquez sur **Modifier**, puis sur **Afficher les détails**.

6.  Dans la page **Modifier le fournisseur fédéré SIP**, vous pouvez taper ou modifier les paramètres suivants :
    
      - **Activer les communications avec ce fournisseur**   la sélection de ce paramètre active les communications avec les utilisateurs de ce fournisseur.
    
      - **Nom du fournisseur :**   une propriété obligatoire, tapez le nom du fournisseur tel qu’il apparaîtra dans la liste des fournisseurs fédérés SIP.
    
      - **Service Edge d’accès (FQDN) :**   une propriété obligatoire, tapez le nom de domaine complet du service Edge d’accès du fournisseur hébergé que vous configurez. Cette information doit être fournie par le fournisseur hébergée et ne doit être modifiée que si le fournisseur hébergé modifie le nom de domaine complet de son service Edge d’accès.
    
      - **Niveau de vérification par défaut :**   le paramètre par défaut, **autoriser les utilisateurs à communiquer avec des personnes de leur liste de contacts qui utilisent ce fournisseur** , limite la communication aux contacts que vous avez acceptés et figurent dans votre liste de contacts.
        
        Sélectionnez **Autoriser les utilisateurs à communiquer avec toutes les personnes qui utilisent ce fournisseur** pour supprimer la restriction sur la réception et l’acceptation d’invitations de contacts. Ce paramètre n’applique aucune restriction sur les personnes qui peuvent vous contacter à partir du réseau du fournisseur hébergé.

7.  Une fois que vous avez configuré les paramètres, cliquez sur **Valider** pour les enregistrer ou sur **Annuler** pour annuler vos modifications.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

