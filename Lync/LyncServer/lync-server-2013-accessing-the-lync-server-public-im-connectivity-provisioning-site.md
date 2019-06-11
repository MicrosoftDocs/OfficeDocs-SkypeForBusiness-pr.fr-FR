---
title: Accès au site d’approvisionnement de connectivité PIC de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a6e028afcd3a9affc6c316b7cb373e124e6d5b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a>Accès au site d’approvisionnement de connectivité PIC de Lync Server à partir de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2019-03-22_

Le processus de mise en service de Lync-connectivité Skype a changé par rapport aux méthodes de mise en service de l’image précédente. Ce processus de mise en service peut durer jusqu’à trente jours. Nous vous recommandons de commencer par commencer ce processus avant d’effectuer les étapes restantes de ce document. Après l’exécution du processus de mise en service de Lync-Skype pour votre compte, le compte est activé et les utilisateurs éligibles sont activés pour la connectivité de messagerie instantanée publique.

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a>Pour configurer Lync-connectivité Skype, vous avez besoin des informations suivantes:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Numéro de contrat Microsoft</p></li>
<li><p>Nom de domaine complet (FQDN) du service Edge d’accès</p></li>
<li><p>Domaine(s) SIP (Session Initiation Protocol)</p></li>
<li><p>Noms complets (FQDN) supplémentaires éventuels du service Edge d’accès</p></li>
<li><p>Coordonnées</p></li>
</ol></td>
</tr>
</tbody>
</table>

À compter du 2019 avril, nous mettrons fin à la collecte et la conservation des informations de contact des clients approvisionnés par Skype Federation par le biais du site Web pic.lync.com. Cette modification est apportée pour s’assurer que le système de mise en service de pic.lync.com respecte les politiques de confidentialité de Microsoft. 

Lorsque le changement est en cours, nous ne pourrons plus fournir de mises à jour par e-mail sur les changements de mise en service en attente. Les modifications apportées aux mises en service PIC s’effectuent généralement dans les 24-48 heures suivant la saisie. Si vous continuez à rencontrer des problèmes avec la Fédération de Skype 48 heures après avoir envoyé une demande de provisionnement, contactez le support technique de Microsoft pour approfondir votre investigation.

> [!IMPORTANT]
> Dans le cadre de cette modification, toutes les informations de contact précédemment entrées sont purgées de notre système à la fin du 1er avril 2019.

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a>Pour démarrer le processus de mise en service de Lync-connectivité Skype:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Connectez-vous au site Web <strong>https://pic.lync.com</strong>, à l’aide de votre identifiant Microsoft Windows Live ID.</p></li>
<li><p>Sélectionnez le type de contrat de licence Microsoft.</p></li>
<li><p>Activez cette case à cocher pour vérifier que vous avez lu et accepté les droits d’utilisation du produit sur Lync Server.</p></li>
<li><p>Dans la page <strong>initier une demande de mise en service</strong> , cliquez sur le lien approprié pour lancer une demande de configuration:</p></li>
<li><p>Dans la page <strong>spécifier les informations de mise en service</strong> , entrez le nom de <strong>domaine complet du service Edge d’accès</strong>. Par exemple, <strong>SIP.contoso.com</strong>.</p>



> [!IMPORTANT]
> Après le 1er juillet, 2017 Microsoft fera en sorte que le déploiement d’enregistrements SRV DNS de Fédération pour la connectivité de messagerie instantanée publique reste opérationnel pour les clients.

</li>
<li><p>Entrez au moins un ou plusieurs noms de domaine SIP, puis cliquez sur <strong>Ajouter</strong>.</p>



> [!IMPORTANT]
> Au moins un serveur Edge d’accès et un domaine SIP sont requis pour terminer le processus de mise en service. Le domaine SIP et le serveur Edge d’accès doivent être actifs, fonctionnels et accessibles sur le réseau.

</li>
<li><p>Dans la liste des <strong>fournisseurs de services de messagerie instantanée publique</strong>, sélectionnez <strong>Skype,</strong> cliquez sur <strong>suivant</strong> pour ajouter des informations de contact, puis envoyez la demande de mise en service.</p></li>
</ol></td>
</tr>
</tbody>
</table>


Après l’envoi de la demande de mise en service, l’activation du compte peut prendre jusqu’à 30 jours et permettre aux utilisateurs d’être activés pour la connectivité de messagerie instantanée publique.

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a>Activation de la fédération et de la connectivité PIC (Public IM Connectivity)

Après avoir soumis la demande de mise en service, vous pouvez vous concentrer sur l’environnement du serveur Lync et les tâches d’administration requises pour configurer Lync-connectivité Skype. Dans cette section, nous supposons que l’administrateur du serveur Lync a déployé Lync Server et configuré l’accès externe. Pour plus d’informations sur la configuration de l’accès externe pour Lync Server, voir «planification pour l’accès [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) utilisateur externe» auprès de et «déploiement de [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)l’accès utilisateur externe».

Pour préparer l’environnement Lync Server pour Lync-connectivité Skype, l’administrateur du serveur Lync doit effectuer les trois tâches suivantes:

<div>

## <a name="1-configure-federation-and-pic"></a>1 \. Configurer la fédération et PIC

La Fédération est requise pour permettre aux utilisateurs de Skype de communiquer avec les utilisateurs de Lync au sein de votre organisation. La connectivité de messagerie instantanée publique (PIC) est une classe de Fédération qui doit être configurée pour permettre aux utilisateurs de Lync de communiquer avec des utilisateurs Skype. Les options de Fédération et PIC sont configurées à l’aide du panneau de configuration de Lync Server, comme illustré ci-dessous.

<div>


> [!IMPORTANT]
> La fédération PIC n’est plus prise en charge par Live Communication Server 2005 SP1 ni par Office Communications Server 2007. Les plateformes prises en charge pour la Fédération PIC incluent Lync Server 2013, Lync Server 2010 et Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2 \. Configurer au moins une stratégie pour la prise en charge de l’accès des utilisateurs fédérés

À l’aide du panneau de configuration de Lync Server, un administrateur doit configurer une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs de Skype peuvent collaborer avec des utilisateurs internes de Lync Server.

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3 \. Configuration du paramètre du fournisseur de PIC Skype pour Lync

À l’aide de Lync Server Management Shell, un administrateur doit configurer la stratégie de client Lync pour afficher Skype en tant que fournisseur de PIC supplémentaire.

<div>


> [!NOTE]
> Les utilisateurs du service PIC ne peuvent pas participer à des sessions de messagerie instantanée ou des conférences dans votre organisation tant que vous n’avez pas configuré au moins une stratégie (étape 2 de cette procédure) pour prendre en charge la connectivité PIC. <BR>Pour configurer la Fédération et la messagerie instantanée, voir Activer ou désactiver la Fédération et la connectivité <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>de messagerie instantanée publique à l’adresse.<BR>Pour configurer au moins une stratégie pour la prise en charge de l’accès des utilisateurs fédérés, voir «Configurer des stratégies <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>pour contrôler l’accès public aux utilisateurs».



</div>

1.  À partir d’un serveur frontal Lync Server, ouvrez Lync Server Management Shell.

2.  Exécutez les deux commandes suivantes :
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > Si vous n’avez pas encore de fournisseur PIC dans votre environnement et que vous êtes en train de créer un nouveau fournisseur de PIC, vous n’avez pas besoin d’exécuter l’applet de action <STRONG>Remove-CsPublicProvider</STRONG> .

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > Ajouté dans Lync Server 2013 CU5 &amp; le client de bureau Lync dans Office 2013 SP1, le NameDecorationRoutingDomain et NameDecorationExcludedDomainList d’améliorer la situation dans laquelle les utilisateurs de Lync ajoutent des contacts Skype nécessaires pour «décorer» des domaines non Microsoft vers Identifiez-les et acheminez-les vers Skype (format: utilisateur (contoso. com) @msn. com). Ces nouveaux paramètres permettent la mise en forme automatique de l’adresse que l’utilisateur entre dans la boîte de dialogue « Ajouter un contact Skype » avec NameDecorationRoutingDomain (qui doit être défini sur msn.com) si elle ne contient pas les domaines dans NameDecorationExcludedDomainList (actuellement, nous pouvons prendre en charge msn.com, live.com, Hotmail.com et outlook.com).

        
        </div>

3.  À partir d’un client Lync, vous pouvez désormais sélectionner Skype en tant que fournisseur de PIC et ajouter un client Skype en spécifiant son compte Microsoft. De plus, un utilisateur de Skype qui a fusionné et connecté avec son compte Microsoft peut envoyer une demande de contact à des utilisateurs de Lync. Pour plus d’informations sur les comptes Microsoft, voir [qu’est-ce qu’un compte Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Pour plus d’informations sur l’ajout de clients à Lync, reportez-vous à la rubrique [utilisation de Lync-connectivité Skype dans Lync Server 2013 en tant qu’utilisateur final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).

4.  Pour plus d’informations sur la modification des fournisseurs hébergés, voir «créer ou modifier des fournisseurs fédérés [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)SIP hébergés» à l’adresse.

Cette procédure termine les tâches d’administration qui doivent être effectuées sur le serveur. Vous êtes désormais configuré pour Lync-connectivité Skype.

</div>

</div>

<div>

## <a name="additional-resources"></a>Ressources supplémentaires

[Utilisation de la connectivité Lync-Skype dans Lync Server 2013 en tant qu’utilisateur final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Guide d’approvisionnement pour la connectivité Lync-Skype dans Lync Server 2013](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

