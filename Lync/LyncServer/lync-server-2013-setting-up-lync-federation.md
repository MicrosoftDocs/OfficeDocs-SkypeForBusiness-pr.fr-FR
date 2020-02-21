---
title: 'Lync Server 2013 : configuration de la Fédération Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cea596f571064a3b72ecbb3b0c2b56c2179aa315
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a>Configuration de la Fédération Lync dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-03-27_

Si vous avez déjà déployé votre ou vos serveurs Edge, l’ajout des fonctionnalités de scénarios fédérés est très rapide. Dans le cas contraire, vous devez commencer par le déploiement des serveurs Edge. Pour plus d’informations, reportez-vous à la rubrique : [planification de l’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-planning-for-external-user-access.md) dans la documentation de planification et [déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement.

<div>


> [!NOTE]  
> Si vous avez l’intention de configurer une combinaison de fédération XMPP, fédération Lync ou connectivité PIC, vous pouvez les déployer simultanément ou l’une après l’autre. Si vous configurez les options à l’aide du Générateur de topologie et de Lync Server Management shell, exécutez l’Assistant Déploiement sur le serveur Edge après avoir configuré les options d’un, de deux ou des trois types de fédération, vous pouvez ainsi réduire le nombre d’étapes nécessaires.



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a>Configuration d’une fédération Lync dans le Générateur de topologie et l’Assistant Déploiement

1.  Sur le serveur frontal, ouvrez le Générateur de topologie. Développez les pools de serveurs Edge, puis cliquez avec le bouton droit sur votre serveur Edge ou votre pool de serveurs Edge. Sélectionnez Modifier les propriétés.

2.  Dans Modifier les propriétés sous Général, sélectionnez Activer la fédération pour ce pool Edge (port 5061). Cliquez sur OK.

3.  Cliquez sur Action, sélectionnez Topologie, puis Publier. Dans la page Publier la topologie, cliquez sur Suivant. Quand la publication est terminée, cliquez sur Terminer.

4.  Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur Installer ou mettre à jour le système Lync Server, puis sur Installer ou supprimer des composants Lync Server. Cliquez sur Réexécuter.

5.  Dans Installer les composants Lync Server, cliquez sur Suivant. L’écran récapitulatif affiche les actions au fur et à mesure qu’elles s’exécutent. Une fois le déploiement terminé, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles. Cliquez sur Terminer pour terminer le déploiement.
    
    <div>
    

    > [!IMPORTANT]  
    > Vous pouvez activer cette option, mais un seul serveur Edge ou pool de serveurs Edge dans votre organisation peut être publié en externe pour la fédération. Tout accès par des utilisateurs fédérés, notamment les utilisateurs de messagerie instantanée publique, passe par le même serveur Edge unique ou pool de serveurs Edge. Par exemple, si votre déploiement inclut un pool de serveurs Edge ou un serveur Edge unique déployé à New York et un déployé à Londres et que vous activez la prise en charge de la fédération sur le pool de serveurs Edge ou le serveur Edge unique de New York, le trafic de signalisation des utilisateurs fédérés passera par le pool de serveurs Edge ou le serveur Edge unique de New York. Ceci s’applique aussi aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le serveur Edge ou le pool de serveurs de Londres pour le trafic A/V.

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a>Configuration d’une fédération avec des partenaires

1.  Pour configurer une Fédération réussie avec un autre Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 ou Office Communicator 2007, sélectionnez le type de Fédération dans le tableau suivant et définissez les enregistrements DNS SRV, l’hôte DNS (A ou AAAA pour IPv6) et configurez les stratégies applicables au type de Fédération :
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Type de fédération</th>
    <th>Enregistrements DNS</th>
    <th>Définition de la stratégie</th>
    <th>Notes</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Domaine partenaire découvert</p></td>
    <td><p>Configurez un enregistrement SRV au format _sipfederationtls. _tcp. &lt;nom&gt;de domaine externe où la valeur de port pour l’enregistrement SRV est TCP 5061 et l' <strong>hôte offrant ce service</strong> est défini en tant que SIP. &lt;nom de domaine&gt; externe : nom de domaine complet de votre service Edge d’accès. Pour plus d’informations sur la création de l’enregistrement SRV <a href="lync-server-2013-configure-dns-for-edge-support.md">, voir Configurer DNS pour la prise en charge du serveur Edge dans Lync Server 2013</a> .</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Activer ou désactiver la découverte des partenaires de Fédération dans Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Les versions précédentes faisaient référence à ce type de fédération sous le nom de <strong>Fédération ouverte améliorée</strong>. La création de l’enregistrement SRV est nécessaire pour ce type de fédération et doit permettre aux autres partenaires de découvrir votre fédération.</p></td>
    </tr>
    <tr class="even">
    <td><p>Domaine partenaire autorisé</p></td>
    <td><p>Configurez un enregistrement SRV au format _sipfederationtls. _tcp. &lt;nom&gt;de domaine externe où la valeur de port pour l’enregistrement SRV est TCP 5061 et l' <strong>hôte offrant ce service</strong> est défini en tant que SIP. &lt;nom de domaine&gt; externe : nom de domaine complet de votre service Edge d’accès. Pour plus d’informations sur la création de l’enregistrement SRV <a href="lync-server-2013-configure-dns-for-edge-support.md">, voir Configurer DNS pour la prise en charge du serveur Edge dans Lync Server 2013</a> .</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Les versions précédentes ont fait référence à ce type de Fédération en tant que <strong>fédération étendue</strong>. La création de l’enregistrement SRV est facultative pour ce type de fédération et doit permettre aux autres partenaires de découvrir votre fédération. Il s’agit alors d’une <strong>Fédération ouverte améliorée</strong>, ou d’un <strong>Domaine partenaire découvert</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p>Serveur partenaire autorisé</p></td>
    <td><p>Configurer le nom de domaine SIP et le nom de domaine complet du serveur Edge partenaire en tant que partenaire de Fédération dans les stratégies</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configurer la prise en charge des domaines externes autorisés dans Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configurer la prise en charge des domaines externes bloqués dans Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Ce type de fédération est la définition d’une relation un-à-un et ne permet pas la découverte d’autres partenaires de fédération. Chaque partenaire de fédération est configuré explicitement. Dans les versions précédentes, on parlait de <strong>Fédération directe</strong></p></td>
    </tr>
    <tr class="even">
    <td><p>Fournisseur d’hébergement et un fournisseur de messagerie instantanée publique</p></td>
    <td><p>Aucune configuration DNS spécifique n’est définie pour ce type de fédération</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Création ou modification de fournisseurs fédérés SIP publics dans Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Créer ou modifier des fournisseurs fédérés SIP hébergés Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Ce type de fédération définit les services et les fournisseurs d’hébergement que vous voulez configurer pour vos utilisateurs. Ils sont généralement utilisés pour configurer des fournisseurs de messagerie instantanée comme Windows Live Messenger, Yahoo! et AOL, ainsi que pour héberger des fournisseurs tels que Lync Online et Office 365</p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !. Messenger jusqu’à la date d’arrêt du service. Date de fin du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</P>
    > <LI>
    > <P>La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo ! Messenger. La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</P>
    > <LI>
    > <P>Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier. La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard. La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  Définir et configurer tout hôte DNS (A ou AAAA pour IPv6) et enregistrements SRV DNS requis

3.  Définissez et configurez les stratégies à l’aide du panneau de configuration Lync Server ou à l’aide de Lync Server Management Shell et des cmdlets appropriées. Pour plus d’informations sur les applets de commande Lync Server Management Shell, voir [Federation and External Access cmdlets dans Lync server 2013](https://docs.microsoft.com/powershell/module/skype/)
    
    <div>
    

    > [!NOTE]  
    > Lync Room System (LRS) n’affiche pas le bouton de jointure pour les réunions envoyées par les organisateurs dans les partenaires Lync fédérés. Pour qu’un lien de participation à une réunion apparaisse sur LRS, l’organisation d’expédition doit activer le format TNEF à l’aide de l’applet de commande suivante :<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>Notez qu’il ne s’agit pas d’un LRS spécifique. Outlook et Lync n’affichent pas non plus de liens de jointure dans ce cas, les propriétés MAPI n’étant pas transportées, mais dans le cas d’Outlook, l’utilisateur peut ouvrir l’invitation à la réunion et cliquer sur l’URL de la réunion. Lorsque TNEFEnabled avec est défini sur true, Exchange 2013 ne supprime pas les propriétés MAPI, y compris OnlineMeetingExternalLink et le bouton de jointure apparaît sur le rappel.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification de SIP, de la Fédération XMPP et de la messagerie instantanée publique dans Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[Gestion de la Fédération et de l’accès externe à Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

