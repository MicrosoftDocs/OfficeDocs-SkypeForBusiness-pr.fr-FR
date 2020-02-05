---
title: 'Lync Server 2013 : Configuration de la fédération Lync'
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
ms.openlocfilehash: 7df0dd85bac0aa3053fb6a3496d6a13fa1f4a85e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a>Configuration de la fédération Lync dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-03-27_

Si vous avez déjà déployé votre serveur ou serveur Edge, l’ajout de fonctionnalités de scénarios fédérés est une avancée directe. Si vous n’avez pas configuré Edge Servers, vous devez commencer par cela. Pour plus d’informations, reportez-vous à la section [planification de l’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-planning-for-external-user-access.md) dans la documentation de planification et [au déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement.

<div>


> [!NOTE]  
> Si vous envisagez de configurer n’importe quelle combinaison de la Fédération XMPP, de la Fédération Lync ou de la connectivité de messagerie instantanée publique, vous pouvez les déployer en même temps. Si vous configurez les options à l’aide du générateur de topologie et de Lync Server Management Shell, puis exécutez l’Assistant Déploiement sur le serveur Edge après avoir configuré les options pour un, deux ou trois types de Fédération, vous pouvez réduire le nombre d’étapes requises.



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a>Configuration de la Fédération Lync dans le générateur de topologie et de l’Assistant Déploiement

1.  Sur un serveur frontal, ouvrez le générateur de topologie. Développez pools de bords, puis cliquez avec le bouton droit sur votre serveur Edge ou sur le pool de serveurs Edge. Sélectionnez modifier les propriétés.

2.  Dans modifier les propriétés sous général, sélectionnez Activer la Fédération pour ce pool Edge (port 5061). Cliquez sur OK.

3.  Cliquez sur action, sélectionnez topologie, puis publier. Lorsque le système vous le demande, cliquez sur suivant. Lorsque la publication est terminée, cliquez sur Terminer.

4.  Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur installer ou mettre à jour le système serveur Lync, puis cliquez sur Configurer ou supprimer les composants Lync Server. Cliquez de nouveau sur Exécuter.

5.  Dans configurer les composants serveur Lync, cliquez sur suivant. L’écran de synthèse indique les actions à mesure qu’elles sont exécutées. Lorsque le déploiement est effectué, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles. Cliquez sur Terminer pour terminer le déploiement.
    
    <div>
    

    > [!IMPORTANT]  
    > Vous pouvez sélectionner cette option, mais un seul pool de périphériques ou serveur de périphérie de votre organisation peut être publié en externe pour la Fédération. Tout accès par des utilisateurs fédérés, y compris des utilisateurs de la messagerie instantanée publique, passe par le même pool de périphérie ou serveur à périphérie unique. Par exemple, si votre déploiement inclut un pool de périphérie ou un serveur Edge unique déployé à New York et un serveur déployé à Londres et que vous activez la prise en charge de la Fédération sur le pool de périphériques de la Nouvelle-York ou sur un serveur de périphérie Pool Edge ou serveur Edge unique. Cela s’applique également aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a>Configuration de la Fédération avec des partenaires

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
    <th>Type de Fédération</th>
    <th>Enregistrements DNS</th>
    <th>Définition de la stratégie</th>
    <th>Remarques</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Domaine partenaire détecté</p></td>
    <td><p>Configurer l’enregistrement SRV du format _sipfederationtls. _tcp. &lt;nom&gt;de domaine externe où la valeur de port pour l’enregistrement SRV est TCP 5061 et l' <strong>hôte proposant ce service</strong> est défini en tant que SIP. &lt;nom de domaine&gt; externe : nom de domaine complet (FQDN) du service Edge d’accès. Pour plus d’informations sur la création de l’enregistrement SRV <a href="lync-server-2013-configure-dns-for-edge-support.md">, voir Configurer la prise en charge de DNS pour Edge dans Lync Server 2013</a> .</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Activation ou désactivation de la découverte de partenaires de fédération dans Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Versions précédentes auxquelles il est fait référence à ce type de Fédération en tant qu’ouverture de la <strong>Fédération avancée</strong>. La création de l’enregistrement SRV est requise pour ce type de Fédération et permet à d’autres partenaires de détecter votre Fédération.</p></td>
    </tr>
    <tr class="even">
    <td><p>Domaine partenaire autorisé</p></td>
    <td><p>Configurer l’enregistrement SRV du format _sipfederationtls. _tcp. &lt;nom&gt;de domaine externe où la valeur de port pour l’enregistrement SRV est TCP 5061 et l' <strong>hôte proposant ce service</strong> est défini en tant que SIP. &lt;nom de domaine&gt; externe : nom de domaine complet (FQDN) du service Edge d’accès. Pour plus d’informations sur la création de l’enregistrement SRV <a href="lync-server-2013-configure-dns-for-edge-support.md">, voir Configurer la prise en charge de DNS pour Edge dans Lync Server 2013</a> .</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Versions précédentes auxquelles il est fait référence à ce type de Fédération comme <strong>Fédération améliorée</strong>. La création de l’enregistrement SRV peut être facultative pour ce type de Fédération et permettre à d’autres partenaires de détecter votre Fédération. Bien entendu, il s’agit d’une <strong>fédération étendue ouverte</strong>ou d’un <strong>domaine partenaire découvert</strong> .</p></td>
    </tr>
    <tr class="odd">
    <td><p>Serveur partenaire autorisé</p></td>
    <td><p>Configurer le nom de domaine SIP et le FQDN du serveur Edge</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configuration de la prise en charge des domaines externes autorisés dans Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configuration de la prise en charge pour les domaines externes bloqués dans Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Ce type de Fédération est la définition d’une relation un-à-un qui ne permet pas la découverte d’autres partenaires de la Fédération. Chaque partenaire de Fédération est configuré explicitement. Dans les versions précédentes, il s’agit de la <strong>Fédération directe</strong></p></td>
    </tr>
    <tr class="even">
    <td><p>Fournisseur d’hébergement et fournisseur de messagerie instantanée publique</p></td>
    <td><p>Aucune configuration DNS spécifique n’est définie pour ce type de Fédération</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Création ou modification des fournisseurs fédérés SIP publics dans Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Création ou modification des fournisseurs fédérés SIP hébergés dans Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Ce type de Fédération définit les services et fournisseurs d’hébergement que vous voulez configurer pour vos utilisateurs. Les utilisations typiques incluent la configuration pour les fournisseurs de messagerie instantanée publique tels que Windows Live Messenger, Yahoo ! et AOL, ainsi que des fournisseurs d’hébergement tels que Lync Online et Office 365</p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo ! Messenger jusqu’à la date d’arrêt du service. Date de fin de vie du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</P>
    > <LI>
    > <P>La fonction USL (PIC) est une licence d’abonnement par mois qui est requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo ! Messenger. La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo !, le contrat sous-jacent pour lequel le son est arrêté.</P>
    > <LI>
    > <P>Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier. La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync. Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  Définissez et configurez tout hôte DNS requis (A ou AAAA pour IPv6) et enregistrements SRV DNS.

3.  Définissez et configurez toutes les stratégies à l’aide du panneau de configuration de Lync Server ou en utilisant Lync Server Management Shell et les applets de commande appropriées. Pour en savoir plus sur les applets de cmdlet Lync Server Management Shell, voir [Fédération et applets de connexion Access externes dans Lync server 2013](https://docs.microsoft.com/powershell/module/skype/)
    
    <div>
    

    > [!NOTE]  
    > Le système de salle Lync (LRS) ne montre pas le bouton de participation pour les réunions envoyées par des organisateurs dans les partenaires Lync fédérés. Pour qu’un lien de participation à une réunion apparaisse sur LRS, l’organisation d’expédition doit activer TNEF en utilisant l’applet de commande suivante :<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>Notez que cela n’est pas spécifique à LRS. Dans le cas contraire, Outlook et Lync n’affichent pas de liens de jointure dans le cas où les propriétés MAPI ne sont pas transportées, mais dans le cas d’Outlook, l’utilisateur peut ouvrir l’invitation à la réunion et cliquer sur l’URL de la réunion. Lorsque TNEFEnabled est défini sur true Exchange 2013 ne Strip pas les propriétés MAPI, y compris OnlineMeetingExternalLink et le bouton Join s’affichera sur le rappel.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification de la Fédération SIP, de XMPP et de la messagerie instantanée publique dans Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[Gestion de la fédération et de l’accès externe à Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

