---
title: 'Lync Server 2013 : Gestion de la fédération et de l’accès externe à Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing federation and external access to Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8eb4dcf6a690e2bab7b834624fb0f695e3e770e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a>Gestion de la fédération et de l’accès externe à Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-10-07_

Le déploiement d’un serveur de périphérie ou d’un pool de périphérie est la première étape de la prise en charge des utilisateurs externes. Pour plus d’informations sur le déploiement de serveurs Edge, voir [déploiement d’un accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement.

Après l’installation et la configuration de votre déploiement interne de Lync Server 2013, les utilisateurs internes au sein de votre organisation peuvent collaborer avec d’autres utilisateurs internes disposant de comptes SIP dans les services de domaine Active Directory (AD DS). La collaboration peut inclure la possibilité d’envoyer et de recevoir des messages instantanés et de mettre à jour le statut de présence et participer à des conférences (également appelées «réunions»). Vous activez et configurez l’accès des utilisateurs externes pour contrôler si les utilisateurs externes pris en charge peuvent collaborer avec des utilisateurs internes de Lync Server. Les utilisateurs externes peuvent inclure des utilisateurs distants de votre déploiement, des utilisateurs fédérés (y compris les utilisateurs pris en charge de fournisseurs de services de messagerie instantanée publique), de Fédération de XMPP et de participants anonymes lors de conférences.

Si votre déploiement incluait l’installation d’un serveur Edge Lync Server 2013 ou d’un pool Edge, l’étendue des types de communication possibles sera considérablement améliorée grâce à un certain nombre d’options pour l’accès utilisateur externe, la communication avec les membres d’autres domaines fédérés SIP. Les fournisseurs fédérés SIP et les utilisateurs fédérés XMPP. Après avoir configuré le serveur de périphérie ou le pool de bords, vous activez les types d’accès des utilisateurs externes que vous souhaitez fournir et configurez les stratégies pour contrôler l’accès externe. Dans Lync Server 2013, vous activez et configurez l’accès et les stratégies des utilisateurs externes à l’aide du panneau de configuration de Lync Server, de Lync Server Management Shell ou les deux, en fonction de la configuration requise pour la tâche. Pour plus d’informations sur ces outils de gestion, reportez-vous à la rubrique [Outils d’administration de Lync server 2013](lync-server-2013-lync-server-administrative-tools.md) dans la documentation opérations, [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) dans la documentation opérations et [installer les outils d’administration de Lync Server 2013. ](lync-server-2013-install-lync-server-administrative-tools.md)dans la documentation opérations.

<div>


> [!IMPORTANT]  
> Lorsque vous concevez votre configuration et vos stratégies pour l’accès des utilisateurs externes, vous devez comprendre la priorité des stratégies et la façon dont elles sont appliquées. Les paramètres de stratégie Lync Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. Le niveau de priorité de la stratégie de serveur Lync est défini comme suit: la stratégie d’utilisateur (la plus influence) a pour effet de remplacer une stratégie de site, puis une stratégie de site remplace une stratégie globale (moins l’influence). Cela signifie que le paramètre de stratégie est plus proche de l’objet affecté par la stratégie, plus l’influence sur l’objet.



</div>

Par défaut, aucune stratégie n’est configurée pour prendre en charge l’accès des utilisateurs externes, y compris l’accès des utilisateurs distants, l’accès des utilisateurs fédérés, même si vous avez déjà activé la prise en charge de l’accès des utilisateurs externes pour votre organisation. Pour contrôler l’utilisation de l’accès des utilisateurs externes, vous devez configurer une ou plusieurs stratégies en spécifiant le type d’accès des utilisateurs externes pris en charge pour chaque stratégie. Cela inclut les stratégies d’accès externe suivantes:

  - **Politique globale la**   stratégie globale est créée lors du déploiement de votre serveur Edge. Par défaut, aucune option d’accès utilisateur externe n’est activée dans la stratégie globale. Pour prendre en charge l’accès des utilisateurs externes au niveau global, vous pouvez configurer la stratégie globale pour prendre en charge un ou plusieurs types d’options d’accès utilisateurs externes. La politique globale s’applique à tous les utilisateurs de votre organisation, mais les stratégies de site et les stratégies d’utilisateur remplacent la stratégie globale. Si vous supprimez la stratégie globale, vous ne la supprimez pas. Au lieu de cela, vous rétablissez la valeur par défaut.

  - **Stratégie de site**   vous pouvez créer et configurer une ou plusieurs stratégies de site pour limiter l’accès des utilisateurs externes à des sites spécifiques. La configuration de la stratégie de site remplace la stratégie globale, uniquement pour le site pour lequel elle est définie. Par exemple, si vous autorisez l’accès des utilisateurs distants dans la stratégie globale, vous pouvez spécifier une stratégie de site qui désactive l’accès des utilisateurs distants pour un site spécifique. Par défaut, une stratégie de site est appliquée à tous les utilisateurs de ce site, mais vous pouvez affecter une stratégie d’utilisateur à un utilisateur pour remplacer le paramètre de stratégie de site.

  - **Stratégie**   de l’utilisateur vous pouvez créer et configurer une ou plusieurs stratégies utilisateur pour limiter la prise en charge de l’accès des utilisateurs distants à des utilisateurs spécifiques. La configuration de la stratégie utilisateur remplace la stratégie globale et la stratégie de site, mais uniquement pour les utilisateurs spécifiques auxquels la stratégie utilisateur est affectée. Par exemple, si vous autorisez l’accès des utilisateurs distants dans la stratégie globale et la stratégie de site, vous pouvez spécifier une stratégie d’utilisateur qui désactive l’accès des utilisateurs distants, puis affecter cette stratégie à des utilisateurs spécifiques. Si vous créez une stratégie d’utilisateur, vous devez l’appliquer à un ou plusieurs utilisateurs avant qu’elle ne soit appliquée.

Pour déterminer les paramètres de configuration et les stratégies à créer ou modifier, reportez-vous aux points de décision suivants:

**Souhaitez-vous autoriser les utilisateurs internes et externes de votre domaine à collaborer à l’aide de la messagerie instantanée, de la conférence Web et de l’audio et de la vidéo?**

Configurez les paramètres comme décrit plus en détail dans les rubriques [Configuration des stratégies pour contrôler l’accès des utilisateurs distants dans Lync server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)et [activez ou désactivez la connectivité de Fédération et de messagerie instantanée publique dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

**Souhaitez-vous autoriser les utilisateurs anonymes à participer à des conférences hébergées par des utilisateurs dans votre déploiement?**

Configurez les paramètres comme décrit dans la rubrique [affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes dans Lync server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), puis [créez ou modifiez une stratégie de conférence dans Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) et les [paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)

**Souhaitez-vous autoriser les utilisateurs à communiquer avec des contacts de domaine fédéré SIP?**

Configurez les paramètres conformément aux rubriques [Configuration des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [activez ou désactivez la connectivité de Fédération et de messagerie instantanée publique dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)et [Gérez les domaines fédérés SIP pour votre Organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

**Si vous avez activé la communication avec les domaines de Fédération SIP, voulez-vous activer les communications avec les contacts de partenariat fédéré XMPP?**

Configurez les paramètres comme décrit dans la rubrique [configurer des stratégies pour contrôler l’accès des utilisateurs fédérés de XMPP dans Lync server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) et [gérer les partenaires fédérés fédérés dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md).

**Si vous avez activé la communication avec des domaines fédérés SIP, voulez-vous activer la découverte automatique de la Fédération SIP?**

Configurez les paramètres comme décrit dans la rubrique [activer ou désactiver la découverte des partenaires de Fédération dans Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

**Si vous avez activé la communication avec les domaines de Fédération SIP, voulez-vous autoriser l’envoi d’une exclusion de responsabilité à des contacts fédérés pour les informer que vous utilisez l’archivage et que ces communications peuvent être archivées?**

Configurez les paramètres comme décrit dans la rubrique [activer ou désactiver l’envoi d’une exclusion d’autorisation d’archivage aux partenaires fédérés de Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Souhaitez-vous autoriser les utilisateurs à communiquer avec des fournisseurs fédérés SIP qui autorisent les communications avec les fournisseurs publics, telles que Windows Live Messenger,\!AOL et Yahoo?**

Configurez les paramètres comme décrit dans les rubriques [Configuration des stratégies pour contrôler l’accès des utilisateurs publics dans Lync server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[activer ou désactiver les options de Fédération et de messagerie instantanée publique dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), puis [créer ou modifier des messages SIP publics fédérés fournisseurs dans Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md).

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity («PIC USL») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Date de fin de vie du 2014 juin pour AOL et Yahoo! a été annoncé. Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</P>
> <LI>
> <P>La fonction USL (PIC) est une licence d’abonnement par mois qui est requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo!, le contrat sous-jacent pour lequel le son est arrêté.</P>
> <LI>
> <P>Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier. La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync. Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.</P></LI></UL>



</div>

**Souhaitez-vous autoriser les utilisateurs à communiquer avec des fournisseurs fédérés SIP qui sont des fournisseurs hébergés exécutant Microsoft Office 365, Microsoft Lync Online et Microsoft Lync Online 2010?**

Configurez les paramètres comme décrit dans la rubrique [créer ou modifier des fournisseurs fédérés SIP dans Lync server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [activer ou désactiver la connectivité de Fédération et de messagerie instantanée publique dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) et [créer ou modifier des fournisseurs fédérés SIP hébergés Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

**Votre déploiement est-il configuré dans un domaine fractionné (également connu sous le nom de domaine hybride) dans lequel certains utilisateurs disposent du serveur principal dans le cadre d’un déploiement local et d’autres utilisateurs sont configurés avec un serveur domestique dans un environnement en ligne?**

Configurez les paramètres comme décrit dans les rubriques [Configuration des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [activez ou désactivez la connectivité de Fédération et de messagerie instantanée publique dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) et [créez ou modifiez un serveur SIP hébergé. fournisseurs Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

Si vous préférez un tableau qui répertorie les exigences:


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
<th>Onglet dans la Fédération et l’accès externe (en travers) ou type d’accès externe (vers le bas)</th>
<th>Stratégie d’accès externe</th>
<th>Configurer Access Edge</th>
<th>Domaines fédérés SIP</th>
<th>Fournisseurs fédérés SIP</th>
<th>Partenaire fédéré de XMPP</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utilisateurs distants</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configuration des stratégies de contrôle d’accès des utilisateurs distants dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013</a></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Contacts fédérés SIP</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Activation ou désactivation de la découverte de partenaires de fédération dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Activation ou désactivation de l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Gestion des domaines fédérés SIP pour l’organisation dans Lync Server 2013</a></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Contacts fédérés de XMPP</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Configuration des stratégies de contrôle d’accès des utilisateurs fédérés XMPP dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></p></td>
<td></td>
<td></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Gestion des partenaires fédérés XMPP dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Domaines partagés/utilisateurs hybrides</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Création ou modification des fournisseurs fédérés SIP hébergés dans Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Contacts du service de messagerie instantanée publique</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Création ou modification des fournisseurs fédérés SIP publics dans Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Accès anonyme aux réunions et aux conférences</p></td>
<td></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Affectation des stratégies de conférence pour la prise en charge les utilisateurs anonymes dans Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Vous devez également tenir compte des paramètres de configuration suivants sous stratégies de conférence: <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">création ou modification d’une stratégie de conférence dans Lync server 2013</A> et les <A href="lync-server-2013-conferencing-policy-settings-reference.md">paramètres de stratégie de conférence pour Lync Server 2013</A>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


Vous pouvez configurer les paramètres d’accès des utilisateurs externes, y compris les stratégies que vous souhaitez utiliser pour contrôler l’accès des utilisateurs externes, même si vous n’avez pas activé l’accès des utilisateurs externes pour votre organisation. Toutefois, les stratégies et autres paramètres que vous configurez ne s’appliquent que si l’accès utilisateur externe est activé pour votre organisation. Les utilisateurs externes ne peuvent pas communiquer avec les utilisateurs de votre organisation lorsque l’accès des utilisateurs externes est désactivé ou s’il n’y a pas de stratégie d’accès des utilisateurs externes pour la prise en charge.

Votre déploiement Edge authentifie les types d’utilisateurs externes (à l’exception des utilisateurs anonymes, qui sont authentifiés par l’ID de conférence et d’une clé d’authentification envoyée au participant anonyme lors de la création de la Conférence et d’invitations aux participants) et de contrôles. Access en fonction de la configuration de votre support Edge. Afin de contrôler les communications, vous pouvez configurer une ou plusieurs stratégies et configurer des paramètres définissant le mode de communication des utilisateurs internes et externes à votre déploiement. Les stratégies et paramètres incluent la stratégie globale par défaut de l’accès des utilisateurs externes, en plus des stratégies de site et d’utilisateur que vous pouvez créer et configurer pour activer un ou plusieurs types d’accès utilisateur externe pour des sites ou des utilisateurs spécifiques.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Gestion de la stratégie d’accès externe dans Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Gestion de la configuration du serveur Edge d’accès pour votre organisation dans Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [Gestion des domaines fédérés SIP pour l’organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [Gestion des fournisseurs fédérés SIP pour l’organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [Gestion des partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [Configuration de la prise en charge de la Fédération pour un client Lync Online dans Lync Server 2013](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

