---
title: 'Lync Server 2013 : création ou modification des fournisseurs fédérés SIP publics'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 795950427023a193eff3ab0012687e381e3d3eff
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a>Création ou modification de fournisseurs fédérés SIP publics dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

La connectivité PIC (Public IM Connectivity) permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs de services de messagerie instantanée fournis par des fournisseurs de services de\!messagerie instantanée publics, notamment Windows Live Messenger, Yahoo et AOL.

Lync Server 2013 possède des configurations de fournisseur public pour America Online, Windows Live et Yahoo\! messagerie instantanée. Chaque fournisseur public est configuré avec le nom de domaine complet du serveur Edge du fournisseur et le niveau de vérification par défaut **permet aux utilisateurs de communiquer uniquement avec des personnes de leur liste de contacts qui utilisent ce fournisseur**.

Par défaut, aucun des fournisseurs publics n’est activé. Terminez le travail relatif au contrat de licence et à l’approvisionnement avant d’activer les fournisseurs publics. Vous pouvez activer le fournisseur avant de terminer le travail relatif au contrat de licence et à l’approvisionnement. Les utilisateurs ne pourront pas communiquer avec leurs contacts situés chez ces fournisseurs tant que le travail préalable ne sera pas terminé. Pour plus d’informations sur la gestion des licences et la mise en service des fournisseurs publics, voir [configure Policies to Control public user Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).

Procédez comme suit pour créer ou modifier des fournisseurs publics :

<div>

## <a name="to-create-or-edit-public-providers"></a>Pour créer ou modifier des fournisseurs publics

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Fournisseurs fédérés SIP**.

4.  Pour créer un fournisseur public, cliquez sur **Nouveau**, puis sur **Fournisseur public**.

5.  Si vous devez modifier une entrée dans la liste des fournisseurs publics, sélectionnez un fournisseur public, cliquez sur **Modifier**, puis sur **Afficher les détails**.

6.  Dans la page **Modifier le fournisseur fédéré SIP**, vous pouvez taper ou modifier les paramètres suivants :
    
      - **Activer les communications avec ce fournisseur**   la sélection de ce paramètre active la messagerie instantanée avec les utilisateurs de ce fournisseur.
    
      - **Nom du fournisseur :**   une propriété obligatoire, tapez le nom du fournisseur tel qu’il apparaîtra dans la liste des fournisseurs fédérés SIP.
    
      - **Service Edge d’accès (FQDN) :**   une propriété obligatoire, tapez le nom de domaine complet du service Edge d’accès du fournisseur que vous configurez. Ces informations sont fournies par défaut et ne doivent être changées que si le fournisseur public modifie le nom de domaine complet du service Edge d’accès au niveau du fournisseur public.
    
      - **Niveau de vérification par défaut :**   le paramètre par défaut, **autoriser les utilisateurs à communiquer avec des personnes de leur liste de contacts qui utilisent ce fournisseur** , limite la communication aux contacts que vous avez acceptés et figurent dans votre liste de contacts.
        
        La sélection du paramètre **Autoriser les utilisateurs à communiquer avec toutes les personnes qui utilisent ce fournisseur** supprime la restriction que vous devez avoir reçue et permet d’accepter l’invitation d’un contact. Ce paramètre n’impose pas de limite aux personnes qui peuvent vous contacter à partir du réseau du fournisseur public.

7.  Quand vous avez terminé de configurer les paramètres, cliquez sur **Valider** pour les enregistrer ou sur **Annuler** pour annuler vos modifications.

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

