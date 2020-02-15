---
title: Accès au site de mise en service de la connectivité PIC de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e640e227ab15c19e48ed3dc06e4b7b482ab7b3a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a>Accès au site de mise en service de la connectivité PIC (Public IM Connectivity) de Lync Server à partir de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2019-03-22_

Le processus de mise en service pour la connectivité Lync-Skype a changé, par rapport aux méthodes de mise en service PIC précédentes. Le processus de mise en service peut prendre jusqu’à 30 jours. Nous vous recommandons de commencer par démarrer ce processus avant d’effectuer les étapes restantes dans ce document. Une fois le processus de mise en service Lync-Skype terminé pour votre compte, le compte est activé et vos utilisateurs éligibles sont activés pour la connectivité PIC.

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a>Pour mettre en service la connectivité Lync-Skype, vous avez besoin des informations suivantes :

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Numéro de contrat Microsoft</p></li>
<li><p>Nom de domaine complet (FQDN) du service Edge d’accès</p></li>
<li><p>Domaine (s) SIP (Session Initiation Protocol)</p></li>
<li><p>Tous les noms de domaine complets du service Edge d’accès supplémentaires</p></li>
<li><p>Informations de contact</p></li>
</ol></td>
</tr>
</tbody>
</table>

À compter du 2019 avril, nous allons arrêter la collecte et la rétention des informations de contact pour les clients qui sont configurés pour la Fédération Skype via le site Web pic.lync.com. Cette modification est effectuée afin de s’assurer que le système de mise en service pic.lync.com adhère aux stratégies de confidentialité de Microsoft. 

Une fois que cette modification a lieu, nous ne pourrons plus fournir de mises à jour de messagerie sur les modifications de mise en service en attente. Les modifications de mise en service PIC se terminent généralement dans les 24-48 heures après leur entrée. Si vous rencontrez toujours des problèmes de Fédération Skype 48 heures après avoir soumis une demande de mise en service, contactez le support technique Microsoft pour en savoir plus.

> [!IMPORTANT]
> Dans le cadre de cette modification, toutes les informations de contact précédemment entrées seront purgées de notre système à la fin du 2019 avril.

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a>Pour lancer le processus de mise en service pour la connectivité Lync-Skype :

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Connectez-vous au site Web <strong>https://pic.lync.com</strong>, à l’aide de votre identifiant Microsoft Windows Live ID.</p></li>
<li><p>Sélectionnez le type de contrat de licence Microsoft.</p></li>
<li><p>Activez la case à cocher, en vérifiant que vous avez lu et accepté les droits d’utilisation du produit pour Lync Server.</p></li>
<li><p>Dans la page <strong>lancer une demande de mise en service</strong> , cliquez sur le lien approprié pour lancer une demande de mise en service :</p></li>
<li><p>Sur la page <strong>spécifier les informations de mise en service</strong> , entrez le nom de <strong>domaine complet du service Edge d’accès</strong>. Par exemple, <strong>SIP.contoso.com</strong>.</p>



> [!IMPORTANT]
> Après le 1er juillet, 2017 Microsoft aura également besoin que l’enregistrement DNS SRV de Fédération déployé pour la connectivité PIC pour continuer à fonctionner.

</li>
<li><p>Entrez au moins un ou plusieurs noms de domaine SIP, puis cliquez sur <strong>Ajouter</strong>.</p>



> [!IMPORTANT]
> Au moins un serveur Edge d’accès et un domaine SIP sont requis pour terminer le processus de mise en service. Le domaine SIP et le serveur Edge d’accès doivent être actifs, opérationnels et accessibles sur le réseau.

</li>
<li><p>Dans la liste des <strong>fournisseurs de services de messagerie instantanée publics</strong>, sélectionnez <strong>Skype,</strong> puis cliquez sur <strong>suivant</strong> pour ajouter des informations de contact, puis envoyez la demande de mise en service.</p></li>
</ol></td>
</tr>
</tbody>
</table>


Une fois la demande de mise en service envoyée, il peut falloir jusqu’à 30 jours pour l’activation du compte et pour que les utilisateurs soient activés pour la connectivité PIC.

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a>Activation de la Fédération et de la connectivité PIC (Public IM Connectivity)

Une fois que vous avez soumis la demande de mise en service, vous pouvez vous concentrer sur l’environnement Lync Server et les tâches administratives requises pour configurer la connectivité Lync-Skype. Dans cette section, nous partons du principe que l’administrateur Lync Server a déployé Lync Server et configuré l’accès externe. Pour plus d’informations sur la configuration de l’accès externe pour Lync Server, voir « Planification de l’accès [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) des utilisateurs externes » à l’adresse et « [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)déploiement de l’accès des utilisateurs externes » à l’adresse.

Pour préparer l’environnement Lync Server pour la connectivité Lync-Skype, l’administrateur Lync Server doit effectuer les trois tâches suivantes :

<div>

## <a name="1-configure-federation-and-pic"></a>1\. Configuration de la Fédération et de PIC

La Fédération est nécessaire pour permettre aux utilisateurs de Skype de communiquer avec des utilisateurs de Lync dans votre organisation. La connectivité PIC (public Instant Messaging Connectivity) est une classe de Fédération et elle doit être configurée pour permettre à vos utilisateurs Lync de communiquer avec des utilisateurs de Skype. La Fédération et PIC sont configurés à l’aide du panneau de configuration Lync Server, comme indiqué ci-dessous.

<div>


> [!IMPORTANT]
> La Fédération PIC n’est plus prise en charge par Live Communication Server 2005 SP1 ou par Office Communications Server 2007. Les plateformes prises en charge pour la Fédération PIC incluent Lync Server 2013, Lync Server 2010 et Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2\. Configurer au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés

À l’aide du panneau de configuration Lync Server, un administrateur doit configurer une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs de Skype peuvent collaborer avec des utilisateurs internes de Lync Server.

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3\. Configurer le paramètre de fournisseur PIC Skype pour Lync

À l’aide de Lync Server Management Shell, un administrateur doit configurer la stratégie de client Lync pour qu’elle affiche Skype en tant que fournisseur PIC supplémentaire.

<div>


> [!NOTE]
> Les utilisateurs des fournisseurs de services PIC (public Instant Messaging Connectivity) ne peuvent pas participer à la messagerie instantanée ou aux conférences de votre organisation tant que vous ne configurez pas au moins une stratégie (étape 2, plus haut dans cette procédure), pour prendre en charge la connectivité PIC.<BR>Pour configurer la Fédération et PIC, voir « Activer ou désactiver la Fédération et la connectivité PIC <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>» à l’adresse.<BR>Pour configurer au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés, voir « Configurer des stratégies pour contrôler <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>l’accès des utilisateurs publics » à l’adresse.



</div>

1.  À partir d’un serveur frontal Lync Server, ouvrez Lync Server Management Shell.

2.  Exécutez les deux commandes suivantes :
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > Si vous n’avez pas encore de fournisseur PIC dans votre environnement et que vous créez un nouveau fournisseur PIC, vous n’avez pas besoin d’exécuter la cmdlet <STRONG>Remove-applet cspublicprovider</STRONG> .

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > Ajouté dans Lync Server 2013 CU5 &amp; client Lync dans Office 2013 SP1, le NameDecorationRoutingDomain et NameDecorationExcludedDomainList améliorent la situation dans laquelle les utilisateurs de Lync ajoutent des contacts Skype nécessaires pour « décorer » des domaines non-Microsoft afin de les identifier et de les acheminer vers Skype (format de : User (contoso. com) @msn. com). Ces nouveaux paramètres autorisent la mise en forme automatique de l’adresse entrée de l’utilisateur dans la boîte de dialogue « Ajouter un contact Skype » avec le NameDecorationRoutingDomain (qui doit être défini sur msn.com) s’il ne contient pas les domaines dans le NameDecorationExcludedDomainList ( Nous pouvons actuellement prendre en charge msn.com, live.com, Hotmail.com, outlook.com).

        
        </div>

3.  À partir d’un client Lync, vous pouvez désormais sélectionner Skype comme fournisseur PIC et ajouter un client Skype en spécifiant son compte Microsoft. En outre, un utilisateur de Skype qui a fusionné et connecté avec son compte Microsoft peut envoyer une demande de contact aux utilisateurs de Lync. Pour plus d’informations sur les comptes Microsoft, consultez [qu’est-ce qu’un compte Microsoft ?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Pour plus d’informations sur l’ajout de clients à Lync, reportez-vous à la rubrique utilisation de la [connectivité Lync-Skype dans Lync Server 2013 en tant qu’utilisateur final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).

4.  Pour plus d’informations sur la modification des fournisseurs hébergés, consultez la rubrique « créer ou modifier des [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)fournisseurs fédérés SIP hébergés » à l’adresse.

Cette opération termine les tâches d’administration qui doivent être effectuées sur le serveur. Vous êtes maintenant configuré pour la connectivité Lync-Skype.

</div>

</div>

<div>

## <a name="additional-resources"></a>Ressources supplémentaires

[Utilisation de la connectivité Lync-Skype dans Lync Server 2013 en tant qu’utilisateur final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Guide de mise en service pour la connectivité Lync-Skype dans Lync Server 2013](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

