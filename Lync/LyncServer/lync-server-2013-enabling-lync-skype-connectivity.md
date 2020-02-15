---
title: 'Lync Server 2013 : activation de la connectivité Lync-Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2b950b8ff778ee48014dc951d89baafab59510c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a>Activation de la connectivité Lync-Skype dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-12-16_

Une fois que vous avez soumis la demande de mise en service, vous pouvez vous concentrer sur l’environnement Lync Server et les tâches administratives requises pour configurer la connectivité Lync-Skype. Dans cette section, nous partons du principe que l’administrateur Lync Server a déployé Lync Server et configuré l’accès externe. Pour plus d’informations sur la configuration de l’accès externe pour Lync Server, consultez la rubrique [planification de l’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-planning-for-external-user-access.md) et [déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

Pour préparer l’environnement Lync Server pour la connectivité Lync-Skype, l’administrateur Lync Server doit effectuer les trois tâches suivantes :

<div>

## <a name="1-configure-federation-and-pic"></a>1\. Configuration de la Fédération et de PIC

La Fédération est nécessaire pour permettre aux utilisateurs de Skype de communiquer avec des utilisateurs de Lync dans votre organisation. La connectivité PIC (public Instant Messaging Connectivity) est une classe de Fédération et elle doit être configurée pour permettre à vos utilisateurs Lync de communiquer avec des utilisateurs de Skype. La Fédération et PIC sont configurés à l’aide du panneau de configuration Lync Server, comme indiqué ci-dessous.

![Affichage de PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Affichage de PIC")

<div>


> [!IMPORTANT]  
> La Fédération PIC n’est plus prise en charge par Live Communication Server 2005 SP1 ou par Office Communications Server 2007. Les plateformes prises en charge pour la Fédération PIC incluent Lync Server 2013, Lync Server 2010 et Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2\. Configurer au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés

À l’aide du panneau de configuration Lync Server, un administrateur doit configurer une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs de Skype peuvent collaborer avec des utilisateurs internes de Lync Server.

![Stratégies](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Stratégies")

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3\. Configurer le paramètre de fournisseur PIC Skype pour Lync

À l’aide de Lync Server Management Shell, un administrateur doit configurer la stratégie de client Lync pour qu’elle affiche Skype en tant que fournisseur PIC supplémentaire.

<div>


> [!NOTE]  
> Les utilisateurs des fournisseurs de services PIC (public Instant Messaging Connectivity) ne peuvent pas participer à des conférences de messagerie instantanée, audio ou vidéo dans votre organisation tant que vous ne configurez pas au moins une stratégie (étape 2, plus haut dans cette procédure), pour prendre en charge la connectivité PIC.



</div>

1.  Pour configurer la Fédération et PIC, voir « Activer ou désactiver la Fédération et la connectivité PIC [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063)» à l’adresse.

2.  Pour configurer au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés, voir « Configurer des stratégies pour contrôler [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)l’accès des utilisateurs publics » à l’adresse.

**Pour modifier un fournisseur de messagerie instantanée Messenger ou Skype existant et le configurer pour Skype**

1.  À partir d’un serveur frontal Lync Server, ouvrez Lync Server Management Shell.

2.  Exécutez les deux commandes suivantes :
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > Si vous n’avez pas encore de fournisseur PIC dans votre environnement et que vous créez un nouveau fournisseur PIC, vous n’avez pas besoin d’exécuter la cmdlet <STRONG>Remove-applet cspublicprovider</STRONG> .

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > Ajouté dans Lync Server 2013 CU5 &amp; client Lync dans Office 2013 SP1, le NameDecorationRoutingDomain et NameDecorationExcludedDomainList améliorent la situation dans laquelle les utilisateurs de Lync ajoutent des contacts Skype nécessaires pour « décorer » des domaines non-Microsoft afin de les identifier et de les acheminer vers Skype (format de : User (contoso. com) @msn. com). Ces nouveaux paramètres autorisent la mise en forme automatique de l’adresse entrée de l’utilisateur dans la boîte de dialogue « Ajouter un contact Skype » avec le NameDecorationRoutingDomain (qui doit être défini sur msn.com) s’il ne contient pas les domaines dans le NameDecorationExcludedDomainList ( Nous pouvons actuellement prendre en charge msn.com, live.com, Hotmail.com, outlook.com).

    
    </div>

3.  À partir d’un client Lync, vous pouvez désormais sélectionner Skype comme fournisseur PIC et ajouter un client Skype en spécifiant son compte Microsoft. En outre, un utilisateur de Skype qui a fusionné et connecté avec son compte Microsoft peut envoyer une demande de contact aux utilisateurs de Lync. Pour plus d’informations sur les comptes Microsoft, consultez [qu’est-ce qu’un compte Microsoft ?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Pour plus d’informations sur l’ajout de clients à Lync, reportez-vous à la rubrique utilisation de la [connectivité Lync-Skype dans Lync Server 2013 en tant qu’utilisateur final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).
    
    ![Ajouter un contact Skype](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Ajouter un contact Skype")

4.  Pour plus d’informations sur la modification des fournisseurs hébergés, consultez la rubrique « créer ou modifier des [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)fournisseurs fédérés SIP hébergés » à l’adresse.

Cette opération termine les tâches d’administration qui doivent être effectuées sur le serveur. Vous êtes maintenant configuré pour la connectivité Lync-Skype.

</div>

</div>

<span> </span>

</div>

</div>

</div>

