---
title: 'Lync Server 2013 : gestion de la Fédération et de l’accès externe à Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing federation and external access to Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2adaff02f6533b463199b5d295f65cc519a784e4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a>Gestion de la Fédération et de l’accès externe à Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-07_

La première étape du processus de définition de la prise en charge des utilisateurs externes consiste à déployer un serveur Edge ou un pool Edge. Pour plus d’informations sur le déploiement des serveurs Edge, voir [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement.

Après avoir installé et configuré votre déploiement interne de Lync Server 2013, les utilisateurs internes au sein de votre organisation peuvent collaborer avec d’autres utilisateurs internes disposant de comptes SIP dans vos services de domaine Active Directory (AD DS). La collaboration peut prendre la forme d’envoi et réception de messages instantanés et de mise à jour du statut de présence ainsi que la participation à des conférences (ou réunions). Vous activez et configurez l’accès des utilisateurs externes pour contrôler si les utilisateurs externes pris en charge peuvent collaborer avec des utilisateurs internes de Lync Server. Les utilisateurs externes peuvent être des utilisateurs distants de votre déploiement, des utilisateurs fédérés (y compris les utilisateurs pris en charge des fournisseurs de services de messagerie instantanée publics), une fédération XMPP ou bien des participants anonymes à des conférences.

Si votre déploiement comprenait l’installation d’un serveur Edge Lync Server 2013 ou d’un pool Edge, l’étendue des types de communication possibles est grandement étendue avec un certain nombre d’options pour l’accès des utilisateurs externes, la communication avec les membres d’autres domaines fédérés SIP, Les fournisseurs fédérés SIP et les utilisateurs fédérés XMPP. Après avoir configuré le serveur Edge ou le pool de serveurs Edge, vous permettez aux types d’accès des utilisateurs externes que vous souhaitez fournir et vous configurez les stratégies pour contrôler l’accès externe. Dans Lync Server 2013, vous activez et configurez les stratégies et l’accès des utilisateurs externes à l’aide du panneau de configuration Lync Server, de Lync Server Management Shell ou des deux, en fonction des besoins de la tâche. Pour plus d’informations sur ces outils de gestion, reportez-vous aux [Outils d’administration de Lync server 2013](lync-server-2013-lync-server-administrative-tools.md) dans la documentation des opérations, [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) dans la documentation des opérations et [installer les outils d’administration Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md) dans la documentation des opérations.

<div>


> [!IMPORTANT]  
> Vous devez bien saisir la priorité des stratégies et la façon dont elles sont appliquées avant de concevoir votre configuration et vos stratégies pour l’accès des utilisateurs externes. Les paramètres de stratégie Lync Server qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Lync Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.



</div>

Par défaut, aucune stratégie n’est configurée pour prendre en charge l’accès des utilisateurs externes, notamment l’accès des utilisateurs distants et des utilisateurs fédérés, même si vous avez déjà activé la prise en charge de l’accès des utilisateurs externes dans votre organisation. Pour contrôler l’accès des utilisateurs externes, vous devez configurer au moins une stratégie, qui spécifie le type d’accès des utilisateurs externes pris en charge. Cela inclut les stratégies d’accès externe suivantes :

  - **Stratégie globale la**   stratégie globale est créée lorsque vous déployez vos serveurs Edge. Par défaut, aucune option d’accès utilisateur externe n’est activée dans la stratégie globale. Pour prendre en charge l’accès des utilisateurs externes au niveau global, vous configurez la stratégie globale pour prendre en charge un ou plusieurs types d’options d’accès des utilisateurs externes. La stratégie globale s’applique à tous les utilisateurs de votre organisation, mais les stratégies de site et les stratégies utilisateur remplacent la stratégie globale. Si vous supprimez la stratégie globale, vous ne la supprimez pas. Au lieu de cela, vous devez rétablir le paramètre par défaut.

  - **Stratégie de site**   vous pouvez créer et configurer une ou plusieurs stratégies de site pour limiter la prise en charge de l’accès des utilisateurs externes à des sites spécifiques. La configuration de la stratégie du site supplante la stratégie globale, uniquement pour le site pour lequel elle est définie. Par exemple, si vous activez l’accès des utilisateurs distants dans la stratégie globale, vous pouvez spécifier une stratégie de site qui désactive l’accès sur un site donné. Par défaut, une stratégie de site s’applique à tous les utilisateurs de ce site, mais vous pouvez affecter une stratégie d’utilisateur qui supplante la configuration de la stratégie de site.

  - **Stratégie utilisateur vous**   pouvez créer et configurer une ou plusieurs stratégies utilisateur pour limiter la prise en charge de l’accès des utilisateurs distants à des utilisateurs spécifiques. La stratégie utilisateur supplante les stratégies globale et de site, uniquement pour les utilisateurs auxquels elle est affectée. Par exemple, si vous activez l’accès des utilisateurs distants dans les stratégies globale et de site, vous pouvez définir une stratégie utilisateur qui désactive l’accès des utilisateurs distants et l’affecter à des utilisateurs spécifiques. Si vous créez une stratégie d’utilisateur, vous devez l’appliquer à un ou plusieurs utilisateurs avant qu’elle n’entre en vigueur.

Pour déterminer les paramètres de configuration et les stratégies à créer ou modifier, reportez-vous aux points de décision suivants :

**Voulez-vous autoriser les utilisateurs internes et externes de votre domaine à collaborer à l’aide de la messagerie instantanée, des conférences web et de l’audio/vidéo ?**

Configurez les paramètres comme indiqué dans les rubriques [configure Policies to Control Remote User Access in Lync server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md), et [activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

**Voulez-vous autoriser les utilisateurs anonymes à participer et être invité à des conférences hébergées par des utilisateurs au sein de votre déploiement ?**

Configurez les paramètres comme indiqué dans la rubrique [attribuer des stratégies de conférence pour prendre en charge les utilisateurs anonymes dans Lync server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [créer ou modifier une stratégie de conférence dans Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) et [référence des paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)

**Voulez-vous autoriser les utilisateurs à communiquer avec des contacts de domaines fédérés SIP ?**

Configurez les paramètres comme indiqué dans les rubriques [configure Policies to Control Federated User Access in Lync server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)et [gestion des domaines fédérés SIP pour votre organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

**Si vous avez activé la communication avec les domaines de fédération SIP, voulez-vous activer les communications avec les contacts partenaires fédérés SIP ?**

Configurez les paramètres comme indiqué dans la rubrique [configure Policies to Control XMPP Federated User Access in Lync server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) et [Manage XMPP Federated Partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md).

**Si vous avez activé la communication avec les domaines fédérés SIP, voulez-vous activer la découverte automatique de la Fédération SIP ?**

Configurez les paramètres comme indiqué dans la rubrique [activation ou désactivation de la découverte des partenaires de Fédération dans Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

**Si vous avez activé la communication avec les domaines de fédération SIP, voulez-vous activer l’envoi d’un dédit de responsabilité aux contacts fédérés leur indiquant que vous utilisez l’archivage et que les communications peuvent être archivées ?**

Configurez les paramètres comme indiqué dans la rubrique [activer ou désactiver l’envoi d’une clause d’exclusion de responsabilité d’archivage aux partenaires fédérés dans Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Souhaitez-vous autoriser les utilisateurs à communiquer avec des fournisseurs fédérés SIP qui permettent la communication avec des fournisseurs publics, tels que Windows Live Messenger, AOL\!et Yahoo ?**

Configurez les paramètres comme indiqué dans les rubriques [configure Policies to Control public user Access dans Lync server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[Enable or Disable Federation and Public IM Connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), et [créez ou modifiez des fournisseurs fédérés SIP publics dans Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md).

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !. Messenger jusqu’à la date d’arrêt du service. Date de fin du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</P>
> <LI>
> <P>La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo ! Messenger. La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</P>
> <LI>
> <P>Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier. La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard. La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</P></LI></UL>



</div>

**Souhaitez-vous autoriser les utilisateurs à communiquer avec des fournisseurs fédérés SIP qui sont des fournisseurs hébergés exécutant Microsoft Office 365, Microsoft Lync Online et Microsoft Lync Online 2010 ?**

Configurez les paramètres comme indiqué dans les rubriques [création ou modification de fournisseurs fédérés SIP publics dans Lync server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) et [création ou modification des fournisseurs fédérés sip hébergés Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

**Votre déploiement est-il configuré dans un domaine séparé (ou domaine hybride), dans lequel certains utilisateurs possèdent leur serveur central dans un déploiement local et d’autres dans un environnement en ligne ?**

Configurez les paramètres comme indiqué dans les rubriques [configure Policies to Control Federated User Access in Lync server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Enable or Disable Federation and Public IM Connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) et [Create or Edit Hosted SIP Federated providers Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

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
<th>Onglet dans Fédération et accès externe (en travers) Fédération ou type d’accès externe (bas)</th>
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
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configurer des stratégies pour contrôler l’accès des utilisateurs distants dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Activer ou désactiver l’accès des utilisateurs distants dans Lync Server 2013</a></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Contacts fédérés SIP</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Activer ou désactiver la découverte des partenaires de Fédération dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Activer ou désactiver l’envoi d’une clause d’exclusion de responsabilité d’archivage aux partenaires fédérés dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Gérer les domaines fédérés SIP pour votre organisation dans Lync Server 2013</a></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Contacts fédérés XMPP</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés XMPP dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</a></p></td>
<td></td>
<td></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Gérer les partenaires fédérés XMPP dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Utilisateurs de domaine séparé/hybride</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Créer ou modifier des fournisseurs fédérés SIP hébergés Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Contacts de services de messagerie instantanée publics</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Création ou modification de fournisseurs fédérés SIP publics dans Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Accès des utilisateurs anonymes aux réunions et conférences</p></td>
<td></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes dans Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Vous devez également prendre en compte les paramètres de configuration suivants sous stratégies de conférence : <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">création ou modification d’une stratégie de conférence dans Lync server 2013</A> et <A href="lync-server-2013-conferencing-policy-settings-reference.md">référence des paramètres de stratégie de conférence pour Lync Server 2013</A>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


Vous pouvez configurer les paramètres d’accès des utilisateurs externes, y compris les stratégies de contrôle de l’accès des utilisateurs externes, même si vous n’avez pas activé l’accès des utilisateurs externes pour votre organisation. Toutefois, les stratégies et les autres paramètres que vous configurez ne prennent effet que lorsque vous activez l’accès des utilisateurs externes pour votre organisation. Les utilisateurs externes ne peuvent pas communiquer avec les utilisateurs de votre organisation si l’accès des utilisateurs externes est désactivé ou si aucune stratégie de prise en charge de l’accès des utilisateurs externes n’a été configurée.

Votre déploiement Edge authentifie les types d’utilisateurs externes (à l’exception des utilisateurs anonymes, qui sont authentifiés par l’ID de conférence et une clé de sécurité envoyée aux participants anonymes lorsque vous créez la conférence et invitez des participants) et contrôle l’accès selon la façon dont vous avez configuré la prise en charge de votre déploiement Edge. Pour contrôler les communications, vous pouvez configurer une ou plusieurs stratégies et des paramètres qui définissent comment les utilisateurs situés en amont ou en aval de votre déploiement communiquent entre eux. Ces stratégies et paramètres incluent la stratégie globale par défaut d’accès des utilisateurs externes, en plus des stratégies de site et utilisateur que vous créez et configurez pour activer un ou plusieurs types d’accès des utilisateurs externes à l’intention de sites ou d’utilisateurs spécifiques.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Gérer la stratégie d’accès externe dans Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Gérer la configuration du serveur Edge d’accès pour votre organisation dans Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [Gérer les domaines fédérés SIP pour votre organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [Gestion des fournisseurs fédérés SIP pour votre organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [Gérer les partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [Configuration de la prise en charge de la Fédération pour un client Lync Online dans Lync Server 2013](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

