---
title: 'Lync Server 2013 : activation de la connectivité Lync-Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 794d2a71c07e742a3ab5597d4bd2aff77157d675
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a>Activation de la connectivité Lync-Skype dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-12-16_

Après avoir soumis la demande de mise en service, vous pouvez vous concentrer sur l’environnement du serveur Lync et les tâches d’administration requises pour configurer Lync-connectivité Skype. Dans cette section, nous supposons que l’administrateur du serveur Lync a déployé Lync Server et configuré l’accès externe. Pour plus d’informations sur la configuration de l’accès externe pour Lync Server, reportez-vous à la rubrique [planification de l’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-planning-for-external-user-access.md) et [déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

Pour préparer l’environnement Lync Server pour Lync-connectivité Skype, l’administrateur du serveur Lync doit effectuer les trois tâches suivantes:

<div>

## <a name="1-configure-federation-and-pic"></a>1 \. Configurer la fédération et PIC

La Fédération est requise pour permettre aux utilisateurs de Skype de communiquer avec les utilisateurs de Lync au sein de votre organisation. La connectivité de messagerie instantanée publique (PIC) est une classe de Fédération qui doit être configurée pour permettre aux utilisateurs de Lync de communiquer avec des utilisateurs Skype. Les options de Fédération et PIC sont configurées à l’aide du panneau de configuration de Lync Server, comme illustré ci-dessous.

![Affichage] de la photo (images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Affichage") de la photo

<div>


> [!IMPORTANT]  
> La fédération PIC n’est plus prise en charge par Live Communication Server 2005 SP1 ni par Office Communications Server 2007. Les plateformes prises en charge pour la Fédération PIC incluent Lync Server 2013, Lync Server 2010 et Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2 \. Configurer au moins une stratégie pour la prise en charge de l’accès des utilisateurs fédérés

À l’aide du panneau de configuration de Lync Server, un administrateur doit configurer une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs de Skype peuvent collaborer avec des utilisateurs internes de Lync Server.

![Politiques] (images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Politiques")

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3 \. Configuration du paramètre du fournisseur de PIC Skype pour Lync

À l’aide de Lync Server Management Shell, un administrateur doit configurer la stratégie de client Lync pour afficher Skype en tant que fournisseur de PIC supplémentaire.

<div>


> [!NOTE]  
> Les utilisateurs des fournisseurs de service de messagerie instantanée publique ne peuvent pas participer à des conférences par messagerie instantanée ou audio ou vidéo dans votre organisation tant que vous n’avez pas configuré au moins une stratégie (étape 2, plus haut dans cette procédure) pour prendre en charge la connectivité de messagerie instantanée publique.



</div>

1.  Pour configurer la Fédération et la messagerie instantanée, voir Activer ou désactiver la Fédération et la connectivité [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063)de messagerie instantanée publique à l’adresse.

2.  Pour configurer au moins une stratégie pour la prise en charge de l’accès des utilisateurs fédérés, voir «Configurer des stratégies [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)pour contrôler l’accès public aux utilisateurs».

**Pour modifier un fournisseur de services de messagerie instantanée ou Skype existant et le configurer pour Skype**

1.  À partir d’un serveur frontal Lync Server, ouvrez Lync Server Management Shell.

2.  Exécutez les deux commandes suivantes :
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > Si vous n’avez pas encore de fournisseur PIC dans votre environnement et que vous êtes en train de créer un nouveau fournisseur de PIC, vous n’avez pas besoin d’exécuter l’applet de action <STRONG>Remove-CsPublicProvider</STRONG> .

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > Ajouté dans Lync Server 2013 CU5 &amp; le client de bureau Lync dans Office 2013 SP1, le NameDecorationRoutingDomain et NameDecorationExcludedDomainList d’améliorer la situation dans laquelle les utilisateurs de Lync ajoutent des contacts Skype nécessaires pour «décorer» des domaines non Microsoft vers Identifiez-les et acheminez-les vers Skype (format: utilisateur (contoso. com) @msn. com). Ces nouveaux paramètres permettent la mise en forme automatique de l’adresse que l’utilisateur entre dans la boîte de dialogue « Ajouter un contact Skype » avec NameDecorationRoutingDomain (qui doit être défini sur msn.com) si elle ne contient pas les domaines dans NameDecorationExcludedDomainList (actuellement, nous pouvons prendre en charge msn.com, live.com, Hotmail.com et outlook.com).

    
    </div>

3.  À partir d’un client Lync, vous pouvez désormais sélectionner Skype en tant que fournisseur de PIC et ajouter un client Skype en spécifiant son compte Microsoft. De plus, un utilisateur de Skype qui a fusionné et connecté avec son compte Microsoft peut envoyer une demande de contact à des utilisateurs de Lync. Pour plus d’informations sur les comptes Microsoft, voir [qu’est-ce qu’un compte Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Pour plus d’informations sur l’ajout de clients à Lync, reportez-vous à la rubrique [utilisation de Lync-connectivité Skype dans Lync Server 2013 en tant qu’utilisateur final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).
    
    ![Ajouter un contact Skype] (images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Ajouter un contact Skype")

4.  Pour plus d’informations sur la modification des fournisseurs hébergés, voir «créer ou modifier des fournisseurs fédérés [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)SIP hébergés» à l’adresse.

Cette procédure termine les tâches d’administration qui doivent être effectuées sur le serveur. Vous êtes désormais configuré pour Lync-connectivité Skype.

</div>

</div>

<span> </span>

</div>

</div>

</div>

