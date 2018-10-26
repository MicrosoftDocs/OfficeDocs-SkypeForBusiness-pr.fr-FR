---
title: "Lync Server 2013 : Gest. de la féd. et de l’accès ext. à Lync Server 2013"
TOCTitle: Gestion de la fédération et de l’accès externe à Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520966(v=OCS.15)
ms:contentKeyID: 49296633
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion de la fédération et de l’accès externe à Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La première étape du processus de définition de la prise en charge des utilisateurs externes consiste à déployer un serveur Edge ou un pool de serveurs Edge. Pour plus d’informations sur le déploiement de serveurs Edge, reportez-vous à [Déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement.

Après avoir installé et configuré votre déploiement interne de Lync Server 2013, les utilisateurs internes de votre organisation peuvent collaborer avec d’autres utilisateurs internes qui disposent d’un compte SIP dans vos services de domaine Active Directory (AD DS). La collaboration peut prendre la forme d’envoi et réception de messages instantanés et de mise à jour du statut de présence ainsi que la participation à des conférences (ou réunions). Vous activez et configurez l’accès des utilisateurs externes pour spécifier si les utilisateurs externes pris en charge peuvent collaborer avec les utilisateurs Lync Server internes. Les utilisateurs externes peuvent être des utilisateurs distants de votre déploiement, des utilisateurs fédérés (dont les utilisateurs pris en charge des fournisseurs de services de messagerie instantanée publics), une fédération XMPP ou bien des participants anonymes à des conférences.

Si votre déploiement a inclus l’installation d’un serveur Edge ou d’un pool de serveurs EdgeLync Server 2013, les types de communication possibles sont considérablement étendus avec un certain nombre d’options pour l’accès des utilisateurs externes, la communication avec des membres d’autres domaines fédérés SIP, des fournisseurs fédérés SIP et des utilisateurs fédérés XMPP. Une fois que vous avez configuré le serveur Edge ou le pool de serveurs Edge, vous devez activer les types d’accès des utilisateurs externes que vous souhaitez prendre en charge et configurer les stratégies permettant de contrôler l’accès externe. Dans Lync Server 2013, vous activez et configurez l’accès des utilisateurs externes et les stratégies à l’aide du Panneau de configuration Lync Server, de Lync Server Management Shell ou des deux, selon les besoins de la tâche. Pour plus d’informations sur ces outils de gestion, reportez-vous à [Outils d’administration de Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md), [Lync Server Management Shell](lync-server-2013-lync-server-management-shell.md) et [Installation des outils d’administration Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md) dans la documentation des opérations.

> [!IMPORTANT]  
> Vous devez bien saisir la priorité des stratégies et la façon dont elles sont appliquées avant de concevoir votre configuration et vos stratégies pour l’accès des utilisateurs externes. Les paramètres de stratégie Lync Server qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Lync Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.

Par défaut, aucune stratégie n’est configurée pour prendre en charge l’accès des utilisateurs externes, dont l’accès des utilisateurs distants et des utilisateurs fédérés, même si vous avez déjà activé la prise en charge de l’accès des utilisateurs externes dans votre organisation. Pour contrôler l’accès des utilisateurs externes, vous devez configurer au moins une stratégie qui spécifie le type d’accès des utilisateurs externes pris en charge, notamment les stratégies d’accès externe suivantes :

  - **Stratégie globale**   La stratégie globale est créée lors du déploiement des serveurs Edge. Par défaut, aucune option d’accès des utilisateurs externes n’est activée dans cette stratégie. Pour prendre en charge l’accès des utilisateurs externes au niveau global, vous devez configurer la stratégie globale pour qu’elle prenne en charge un ou plusieurs types d’option d’accès des utilisateurs externes. La stratégie globale s’applique à tous les utilisateurs de votre organisation. Cependant, les stratégies de niveau site et utilisateur la supplantent. Si vous supprimez la stratégie globale, il n’est pas nécessaire de la retirer. Il suffit de rétablir ses paramètres par défaut.

  - **Stratégie de site**   Vous pouvez créer et configurer une ou plusieurs stratégies de site pour limiter la prise en charge de l’accès des utilisateurs externes à des sites spécifiques. La stratégie de site supplante la stratégie globale, uniquement pour le site pour lequel elle est définie. Par exemple, si vous activez l’accès des utilisateurs distants dans la stratégie globale, vous pouvez spécifier une stratégie de site qui désactive l’accès sur un site donné. Par défaut, une stratégie de site s’applique à tous les utilisateurs de ce site. Vous pouvez affecter une stratégie utilisateur qui supplante la stratégie de site.

  - **Stratégie utilisateur**   Vous pouvez créer et configurer une ou plusieurs stratégies utilisateur pour limiter la prise en charge de l’accès des utilisateurs distants à des utilisateurs spécifiques. La stratégie utilisateur supplante les stratégies globale et de site, uniquement pour les utilisateurs auxquels elle est affectée. Par exemple, si vous activez l’accès des utilisateurs distants dans les stratégies globale et de site, vous pouvez définir une stratégie utilisateur qui désactive l’accès des utilisateurs distants et l’affecter à des utilisateurs spécifiques. Si vous créez une stratégie utilisateur, vous devez l’appliquer à un ou plusieurs utilisateurs pour qu’elle prenne effet.

Pour déterminer les paramètres de configuration et les stratégies à créer ou modifier, reportez-vous aux points de décision suivants :

**Voulez-vous autoriser les utilisateurs internes et externes de votre domaine à collaborer à l’aide de la messagerie instantanée, des conférences web et de l’audio/vidéo ?**

Configurez les paramètres comme indiqué dans les rubriques [Configuration des stratégies de contrôle d’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) et [Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

**Voulez-vous autoriser les utilisateurs anonymes à participer et être invité à des conférences hébergées par des utilisateurs au sein de votre déploiement ?**

Configurez les paramètres comme indiqué dans les rubriques [Affectation des stratégies de conférence pour la prise en charge les utilisateurs anonymes dans Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [Création ou modification d’une stratégie de conférence dans Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) et [Référence des paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)

**Voulez-vous autoriser les utilisateurs à communiquer avec des contacts de domaines fédérés SIP ?**

Configurez les paramètres comme indiqué dans les rubriques [Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) et [Gestion des domaines fédérés SIP pour l’organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

**Si vous avez activé la communication avec les domaines de fédération SIP, voulez-vous activer les communications avec les contacts partenaires fédérés SIP ?**

Configurez les paramètres comme indiqué dans les rubriques [Configuration des stratégies de contrôle d’accès des utilisateurs fédérés XMPP dans Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md), [Gestion des partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md).

**Si vous avez activé la communication avec les domaines fédérés SIP, voulez-vous activer la découverte automatique de fédération SIP ?**

Configurez les paramètres comme indiqué dans la rubrique [Activation ou désactivation de la découverte de partenaires de fédération dans Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

**Si vous avez activé la communication avec les domaines de fédération SIP, voulez-vous activer l’envoi d’un dédit de responsabilité aux contacts fédérés leur indiquant que vous utilisez l’archivage et que les communications peuvent être archivées ?**

Configurez les paramètres comme indiqué dans la rubrique [Activation ou désactivation de l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés dans Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Voulez-vous autoriser les utilisateurs à communiquer avec des fournisseurs fédérés SIP qui permettent la communication avec des fournisseurs publics, tels que Windows Live Messenger, AOL et Yahoo\! ?**

Configurez les paramètres comme indiqué dans les rubriques [Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md), [Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) et [Création ou modification des fournisseurs fédérés SIP publics dans Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md)

> [!IMPORTANT]  
> <ul>
> <li><p>Depuis le 1er septembre 2012, la licence Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License) n’est plus disponible et ne peut pas être achetée ou renouvelée. Les clients disposant de licences actives pourront continuer à assurer la fédération avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Une date de fin de vie de juin 2014 a été annoncée pour AOL et Yahoo! Pour plus d’informations, reportez-vous à <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013</a>.</p></li>
> <li><p>La licence PIC USL est une licence d’abonnement mensuel par utilisateur requise pour la fédération de Lync Server ou Office Communications Server avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est liée au soutien de Yahoo!, dont le contrat sous-jacent arrive à expiration.</p></li>
> <li><p>Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. La fédération avec Skype sera prochainement ajoutée à cette liste, ce qui permettra aux utilisateurs Lync d’entrer en contact avec des centaines de millions de personnes à l’aide des fonctionnalités vocales et de messagerie instantanée.</p></li></ul>


**Voulez-vous autoriser les utilisateurs à communiquer avec des fournisseurs fédérés SIP qui sont des fournisseurs hébergés exécutant Microsoft Office 365, Microsoft Lync Online et Microsoft Lync Online 2010 ?**

Configurez les paramètres comme indiqué dans les rubriques [Création ou modification des fournisseurs fédérés SIP publics dans Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) et [Création ou modification des fournisseurs fédérés SIP hébergés dans Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

**Votre déploiement est-il configuré dans un domaine distinct (ou domaine hybride), dans lequel certains utilisateurs possèdent leur serveur central dans un déploiement local et d’autres dans un environnement en ligne ?**

Configurez les paramètres comme indiqué dans les rubriques [Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) et [Création ou modification des fournisseurs fédérés SIP hébergés dans Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

Vous trouverez ci-après un tableau récapitulant les conditions requises :


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Onglet dans Fédération et Accès externe (Latéralement) Fédération ou type d’accès externe (Bas)</th>
<th>Stratégie d’accès externe</th>
<th>Configuration du serveur Edge d’accès</th>
<th>Domaines fédérés SIP</th>
<th>Fournisseurs fédérés SIP</th>
<th>Partenaire fédéré XMPP</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utilisateurs distants</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configuration des stratégies de contrôle d’accès des utilisateurs distants dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013</a></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Contacts fédérés SIP</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013</a></p>
<p></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Activation ou désactivation de la découverte de partenaires de fédération dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Activation ou désactivation de l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Gestion des domaines fédérés SIP pour l’organisation dans Lync Server 2013</a></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Contacts fédérés XMPP</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Configuration des stratégies de contrôle d’accès des utilisateurs fédérés XMPP dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Gestion des partenaires fédérés XMPP dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Utilisateurs de domaine distinct/hybride</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Création ou modification des fournisseurs fédérés SIP hébergés dans Lync Server 2013</a></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Contacts de services de messagerie instantanée publics</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Création ou modification des fournisseurs fédérés SIP publics dans Lync Server 2013</a></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Accès des utilisateurs anonymes aux réunions et conférences</p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Affectation des stratégies de conférence pour la prise en charge les utilisateurs anonymes dans Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Vous devez aussi considérer les paramètres de configuration suivants sous Stratégies de conférence : <a href="lync-server-2013-create-or-modify-a-conferencing-policy.md">Création ou modification d’une stratégie de conférence dans Lync Server 2013</a> et <a href="lync-server-2013-conferencing-policy-settings-reference.md">Référence des paramètres de stratégie de conférence pour Lync Server 2013</a>
</div></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


Vous pouvez configurer les paramètres d’accès des utilisateurs externes, dont les stratégies de contrôle de l’accès des utilisateurs externes, même si vous n’avez pas activé l’accès des utilisateurs externes pour votre organisation. Cependant, les stratégies et les autres paramètres que vous configurez ne prennent effet que lorsque vous activez l’accès des utilisateurs externes pour votre organisation. Les utilisateurs externes ne peuvent pas communiquer avec les utilisateurs de votre organisation si l’accès des utilisateurs externes est désactivé ou si aucune stratégie de prise en charge de l’accès des utilisateurs externes n’a été configurée.

Votre déploiement Edge authentifie les types d’utilisateurs externes (à l’exception des utilisateurs anonymes, lesquels sont authentifiés par l’ID de conférence et une clé d’accès envoyée au participant anonyme quand vous créez la conférence et invitez des participants) et contrôle l’accès selon la façon dont vous avez configuré la prise en charge de votre déploiement Edge. Pour contrôler les communications, vous pouvez configurer une ou plusieurs stratégies et des paramètres qui définissent comment les utilisateurs internes ou externes à votre déploiement communiquent entre eux. Les stratégies et les paramètres sont notamment la stratégie globale par défaut d’accès des utilisateurs externes, en plus des stratégies de site et d’utilisateur que vous créez et configurez pour activer un ou plusieurs types d’accès des utilisateurs externes à l’intention de sites ou d’utilisateurs spécifiques.

## Dans cette section

  - [Gestion de la stratégie d’accès externe dans Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Gestion de la configuration du serveur Edge d’accès pour votre organisation dans Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [Gestion des domaines fédérés SIP pour l’organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [Gestion des fournisseurs fédérés SIP pour l’organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [Gestion des partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [Configuration de la prise en charge de la fédération pour un client Lync Online 2013](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

