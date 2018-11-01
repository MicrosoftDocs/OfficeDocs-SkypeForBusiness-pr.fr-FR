---
title: 'Lync Server 2013 : Configuration de la fédération Lync'
TOCTitle: Configuration de la fédération Lync
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204800(v=OCS.15)
ms:contentKeyID: 49296860
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la fédération Lync dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Si vous avez déjà déployé votre ou vos serveurs Edge, l’ajout des fonctionnalités de scénarios fédérés est très rapide. Dans le cas contraire, vous devez commencer par le déploiement des serveurs Edge. Pour plus d’informations, reportez-vous à : [Planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) dans la documentation de planification et [Déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement.

> [!NOTE]  
> Si vous avez l’intention de configurer une combinaison de fédération XMPP, fédération Lync ou connectivité PIC, vous pouvez les déployer simultanément ou l’une après l’autre. Si vous configurez les options à l’aide du générateur de topologie et de Lync Server Management shell, exécutez l’Assistant Déploiement sur le serveur Edge après avoir configuré les options d’un, de deux ou des trois types de fédération, vous pouvez ainsi réduire le nombre d’étapes nécessaires.

## Configuration d’une fédération Lync dans le générateur de topologie et l’Assistant Déploiement

1.  Sur le serveur frontal, ouvrez le générateur de topologie. Développez les pools de serveurs Edge, puis cliquez avec le bouton droit sur votre serveur Edge ou votre pool de serveurs Edge. Sélectionnez Modifier les propriétés.

2.  Dans Modifier les propriétés sous Général, sélectionnez Activer la fédération pour ce pool Edge (port 5061). Cliquez sur OK.

3.  Cliquez sur Action, sélectionnez Topologie, puis Publier. Dans la page Publier la topologie, cliquez sur Suivant. Quand la publication est terminée, cliquez sur Terminer.

4.  Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur Installer ou mettre à jour le système Lync Server, puis sur Installer ou supprimer des composants Lync Server. Cliquez sur Réexécuter.

5.  Dans Installer les composants Lync Server, cliquez sur Suivant. L’écran récapitulatif affiche les actions au fur et à mesure qu’elles s’exécutent. Une fois le déploiement terminé, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles. Cliquez sur Terminer pour terminer le déploiement.
    
    > [!IMPORTANT]  
    > Vous pouvez activer cette option, mais un seul serveur Edge ou pool de serveurs Edge dans votre organisation peut être publié en externe pour la fédération. Tout accès par des utilisateurs fédérés, notamment les utilisateurs de messagerie instantanée publique, passe par le même serveur Edge unique ou pool de serveurs Edge. Par exemple, si votre déploiement inclut un pool de serveurs Edge ou un serveur Edge unique déployé à New York et un déployé à Londres et que vous activez la prise en charge de la fédération sur le pool de serveurs Edge ou le serveur Edge unique de New York, le trafic de signalisation des utilisateurs fédérés passera par le pool de serveurs Edge ou le serveur Edge unique de New York. Cela s’applique aussi aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le serveur Edge ou le pool de serveurs de Londres pour le trafic A/V.

## Configuration d’une fédération avec des partenaires

1.  Pour configurer correctement une fédération avec un autre Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 ou Office Communicator 2007, sélectionnez le type de fédération à partir du tableau suivant et définissez les enregistrements SRV DNS, l’hôte DNS (A ou AAAA pour IPv6) et configurez les stratégies applicables au type de fédération :
    

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
    <th>Remarques</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Domaine partenaire découvert</p></td>
    <td><p>Configurez l’enregistrement SRV au format _sipfederationtls._tcp.&lt;nom de domaine externe&gt;où la valeur du port pour l’enregistrement SRV est TCP 5061 et <strong>Hôte offrant ce service</strong> a la valeur sip. &lt;nom de domaine externe&gt; – le nom de domaine complet de votre service Edge d’accès. Reportez-vous à <a href="lync-server-2013-configure-dns-for-edge-support.md">Configuration de DNS pour la prise en charge de périphérie dans Lync Server 2013</a> pour obtenir des détails sur la création de l’enregistrement SRV</p></td>
    <td><ul>    
<li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></p></li>    
<li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Activation ou désactivation de la découverte de partenaires de fédération dans Lync Server 2013</a></p></li>    </ul></td>
    <td><p>Les versions précédentes faisaient référence à ce type de fédération sous le nom de <strong>Fédération ouverte améliorée</strong>. La création de l’enregistrement SRV est nécessaire pour ce type de fédération et doit permettre aux autres partenaires de découvrir votre fédération.</p></td>
    </tr>
    <tr class="even">
    <td><p>Domaine partenaire autorisé</p></td>
    <td><p>Configurez l’enregistrement SRV au format _sipfederationtls._tcp.&lt;nom de domaine externe&gt;où la valeur du port pour l’enregistrement SRV est TCP 5061 et <strong>Hôte offrant ce service</strong> a la valeur sip. &lt;nom de domaine externe&gt; – le nom de domaine complet de votre service Edge d’accès. Reportez-vous à <a href="lync-server-2013-configure-dns-for-edge-support.md">Configuration de DNS pour la prise en charge de périphérie dans Lync Server 2013</a> pour obtenir des détails sur la création de l’enregistrement SRV</p></td>
    <td><ul>    
<li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></p></li>    </ul></td>
    <td><p>Les versions précédentes faisaient référence à ce type de fédération sous le nom de <strong>Fédération améliorée</strong>. La création de l’enregistrement SRV est facultative pour ce type de fédération et doit permettre aux autres partenaires de découvrir votre fédération. Il s’agit alors d’une <strong>Fédération ouverte améliorée</strong>, ou d’un <strong>Domaine partenaire découvert</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p>Serveur partenaire autorisé</p></td>
    <td><p>Configurez le nom de domaine SIP et le nom de domaine complet du serveur Edge partenaire en tant que partenaire de fédération dans Stratégies</p></td>
    <td><ul>    
<li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></p></li>    
<li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configuration de la prise en charge des domaines externes autorisés dans Lync Server 2013</a></p></li>    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configuration de la prise en charge pour les domaines externes bloqués dans Lync Server 2013</a></p></li>    </ul></td>
    <td><p>Ce type de fédération est la définition d’une relation un-à-un et ne permet pas la découverte d’autres partenaires de fédération. Chaque partenaire de fédération est configuré explicitement. Dans les versions précédentes, on parlait de <strong>Fédération directe</strong></p></td>
    </tr>
    <tr class="even">
    <td><p>Fournisseur d’hébergement et fournisseur de messagerie instantanée public</p></td>
    <td><p>Aucune configuration DNS spécifique n’est définie pour ce type de fédération</p></td>
    <td><ul>    
<li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></p></li>    
<li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Création ou modification des fournisseurs fédérés SIP publics dans Lync Server 2013</a></p></li>    
<li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Création ou modification des fournisseurs fédérés SIP hébergés dans Lync Server 2013</a></p></li>    </ul></td>
    <td><p>Ce type de fédération définit les services et les fournisseurs d’hébergement que vous voulez configurer pour vos utilisateurs. Ils sont généralement utilisés pour configurer des fournisseurs de messagerie instantanée comme Windows Live Messenger, Yahoo! et AOL, ainsi que pour héberger des fournisseurs tels que Lync Online et Office 365</p>
    <div>

> [!IMPORTANT]  
> <ul> <li><p>Depuis le 1er septembre 2012, la licence Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License) n’est plus disponible et ne peut pas être achetée ou renouvelée. Les clients disposant de licences actives pourront continuer à assurer la fédération avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Une date de fin de vie de juin 2014 a été annoncée pour AOL et Yahoo! Pour plus d’informations, reportez-vous à <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013</a>.</p></li>    
> <li><p>La licence PIC USL est une licence d’abonnement mensuel par utilisateur requise pour la fédération de Lync Server ou Office Communications Server avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est liée au soutien de Yahoo!, dont le contrat sous-jacent arrive à expiration.</p></li>    
> <li><p>Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. La fédération avec Skype sera prochainement ajoutée à cette liste, ce qui permettra aux utilisateurs Lync d’entrer en contact avec des centaines de millions de personnes à l’aide des fonctionnalités vocales et de messagerie instantanée.</p></li>    </ul>
</div></td>
    </tr>
    </tbody>
    </table>
    


2.  Définir et configurer les hôtes DNS (A ou AAAA pour IPv6) et les enregistrements SRV DNS requis

3.  Définir et configurer des stratégies dans le Panneau de configuration Lync Server ou Lync Server Management Shell et à l’aide des applets de commande appropriées. Pour plus d’informations sur les applets de commande Lync Server Management Shell, reportez-vous à [Cmdlets de fédération et d’accès externe dans Lync Server 2013](https://docs.microsoft.com/en-us/powershell/module/skype/)
    
    > [!NOTE]  
    > Lync Room System (LRS) n’affiche pas le bouton Participer pour les réunions envoyées par les organisateurs dans les partenaires Lync fédérés. Pour qu’un lien de participation à une réunion apparaisse sur LRS, l’organisation émettrice doit activer TNEF en utilisant l’applet de commande suivante :<br />
    <br />
    <code>New-RemoteDomain -DomainName Contoso.com -Name Contoso</code><br />
    <code>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</code><br />
    Notez que cela n’est pas spécifique à LRS. Outlook et Lync n’affichent pas non plus les liens de participation dans ce cas, car les propriétés MAPI ne sont pas transportées, mais, dans le cas d’Outlook, l’utilisateur peut ouvrir l’invitation à la réunion et cliquer sur l’URL de la réunion. Lorsque TNEFEnabled présente la valeur True, Exchange 2013 ne supprime pas les propriétés MAPI, dont OnlineMeetingExternalLink et le bouton Participer s’affiche sur le rappel.

## Voir aussi

#### Autres ressources

[Planification pour la fédération SIP, la fédération XMPP et la messagerie instantanée publique dans Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[Gestion de la fédération et de l’accès externe à Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)

