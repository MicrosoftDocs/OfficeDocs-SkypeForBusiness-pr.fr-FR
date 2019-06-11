---
title: 'Lync Server 2013 : Création ou modification des fournisseurs fédérés SIP publics'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 876a79e840990afb0c9cf0bae4fc819ec10db5d8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a>Création ou modification des fournisseurs fédérés SIP publics dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-19_

La connectivité de messagerie instantanée publique permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs de services de messagerie instantanée proposés par des fournisseurs de services de messagerie instantanée\!publics, y compris Windows Live Messenger, Yahoo et AOL.

Lync Server 2013 possède des configurations de fournisseur public pour America Online, Windows Live et Yahoo\! messagerie instantanée. Chaque fournisseur public est configuré à l’aide du nom de domaine complet du serveur Edge du fournisseur et le niveau de vérification par défaut **permet aux utilisateurs de communiquer uniquement avec des personnes figurant sur leur liste de contacts qui utilisent ce fournisseur**.

Comme paramètre par défaut, aucun des fournisseurs publics n’est activé. Vous devez compléter le contrat de licence et le fonctionnement de la mise en service avant d’activer les fournisseurs publics. Vous pouvez activer le fournisseur avant d’effectuer les tâches de gestion des licences et de mise en service. Les utilisateurs ne seront pas en mesure de communiquer avec les contacts de ces fournisseurs tant que la configuration requise ne sera pas effectuée. Pour plus d’informations sur la gestion des licences et la mise en service des fournisseurs publics, voir [configurer des stratégies pour contrôler l’accès des utilisateurs publics dans Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).

Pour créer ou modifier des fournisseurs publics, procédez comme suit:

<div>

## <a name="to-create-or-edit-public-providers"></a>Pour créer ou modifier des fournisseurs publics

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **fournisseurs fédérés SIP**.

4.  Si vous avez besoin de créer un nouveau fournisseur public, cliquez sur **nouveau** , puis cliquez sur **fournisseur public**.

5.  Si vous devez modifier une entrée dans la liste des fournisseurs publics, sélectionnez un fournisseur public, cliquez sur **modifier**, puis sur **afficher les détails**.

6.  Dans la page **modifier le fournisseur fédéré SIP** , vous pouvez taper ou modifier les paramètres suivants:
    
      - **Activer les communications avec ce fournisseur**   sélectionnez ce paramètre active la messagerie instantanée avec les utilisateurs de ce fournisseur.
    
      - **Nom du fournisseur:**   une propriété requise, tapez le nom du fournisseur tel qu’il sera reflété dans la liste des fournisseurs fédérés SIP.
    
      - **Service Edge d’accès (FQDN):**   une propriété requise, tapez le nom de domaine complet du service Edge d’accès du fournisseur que vous configurez. Ces informations sont fournies en tant qu’élément par défaut et ne doivent être changées que si le fournisseur public apporte une modification au FQDN du service Edge d’accès au fournisseur public.
    
      - **Niveau de vérification par défaut:**   le paramètre par défaut, **permettre aux utilisateurs de communiquer avec des personnes de la liste de contacts qui utilisent ce fournisseur** , limite les communications aux contacts que vous avez acceptés et qui se trouvent dans votre liste de contacts.
        
        Sélectionner **permettre aux utilisateurs de communiquer avec tout le monde à l’aide de ce fournisseur** supprime la restriction que vous devez avoir reçu et accepté une invitation de contact. Ce paramètre ne limite pas les personnes qui peuvent vous contacter à partir du réseau du fournisseur public.

7.  Lorsque vous avez configuré les paramètres, cliquez sur **valider** pour enregistrer ou cliquez sur **Annuler** pour ignorer vos modifications.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

