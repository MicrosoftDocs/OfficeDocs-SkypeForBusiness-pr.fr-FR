---
title: Configuration de l’intégration de Lync Server sur site avec Exchange Online
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c4900beab738f9aa792919cceec015bb0c3ad0f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a>Configuration de l’intégration de Lync Server 2013 sur site à Exchange Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2018-03-30_

Les clients qui utilisent des déploiements Lync Server 2013 sur site peuvent configurer l’interopérabilité avec Microsoft Outlook Web App dans Microsoft Exchange Online dans un mode de déploiement hybride. Les fonctionnalités d’interopérabilité comprennent l’ouverture de session unique et l’intégration de la messagerie instantanée et de la présence avec l’interface d’Outlook Web App. Pour activer cette intégration, vous devez configurer le serveur Edge dans votre déploiement Lync Server local en effectuant les tâches suivantes :

  - configurer un espace d’adressage SIP partagé ;

  - Configurer un fournisseur d’hébergement sur le serveur Edge

  - Vérifier la réplication du magasin central de gestion mis à jour

Si Lync Server 2013 est intégré à Exchange Online, un utilisateur qui tente de se connecter à la messagerie instantanée depuis OWA est considéré comme un utilisateur distant ou externe. Dans ce scénario, l’utilisateur doit avoir une stratégie d’accès externe assignée dont l’option suivante est sélectionnée :

**Autoriser les communications avec des utilisateurs distants**

Activez cette option si vous souhaitez que les utilisateurs de votre organisation qui se trouvent à l’extérieur de votre pare-feu, tels que les télétravailleurs et les utilisateurs qui sont en déplacement, puissent se connecter à Lync Server via Internet.

Pour plus d’informations, consultez la rubrique [gestion de la stratégie d’accès externe dans Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).

<div>

## <a name="configure-a-shared-sip-address-space"></a>Configurer un espace d’adressage SIP partagé

Pour intégrer Lync Server 2013 sur site à Exchange Online, vous devez configurer un espace d’adressage SIP partagé. Le même espace d’adressage de domaine SIP est pris en charge par Lync Server et le service Exchange Online.

À l’aide de Lync Server Management Shell, configurez le serveur Edge pour la Fédération en exécutant la cmdlet **Set-CSAccessEdgeConfiguration** à l’aide des paramètres affichés dans l’exemple suivant :

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - **AllowFederatedUsers** indique si des utilisateurs internes sont autorisés à communiquer avec des utilisateurs de domaines fédérés. Cette propriété détermine également si les utilisateurs internes peuvent communiquer avec des utilisateurs dans un scénario d’espace d’adressage SIP partagé avec Lync Server et Exchange Online.

Pour plus d’informations sur l’utilisation de Lync Server Management Shell, voir [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurer un fournisseur d’hébergement sur le serveur Edge.

Utilisez Lync Server Management Shell pour configurer un fournisseur d’hébergement sur le serveur Edge. Pour ce faire, exécutez la cmdlet **New-CsHostingProvider** à l’aide des paramètres de l’exemple suivant :

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> Si vous utilisez Office 365 géré par 21Vianet en Chine, remplacez la valeur du paramètre <STRONG>ProxyFqdn</STRONG> dans cet exemple ("EXAP.um.Outlook.com") par le nom de domaine complet (FQDN) du service géré par 21ViaNet : "EXAP.um.Partner.Outlook.CN".



</div>

  - **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez (par exemple, « Exchange Online »). Les valeurs qui contiennent des espaces doivent être placées entre guillemets doubles.

  - **Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Elle doit être définie sur **true**.

  - **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adressage SIP partagé. Elle doit être définie sur **true**.

  - **HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger Office Communications Server ou Lync Server. Il doit avoir la valeur **false**.

  - **ProxyFQDN** spécifie le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement. Pour Exchange Online, le nom de domaine complet est exap.um.outlook.com.

  - **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Lync Server. Il doit avoir la valeur **false**.

  - **VerificationLevel** indique le niveau de vérification autorisé pour les messages échangés avec le fournisseur hébergé. Spécifiez **UseSourceVerification**. Cette option repose sur le niveau de vérification inclus dans les messages envoyés par le fournisseur d’hébergement. Si ce niveau n’est pas spécifié, le message sera rejeté comme non vérifiable.

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a>Vérifier la réplication du magasin central de gestion mis à jour

Les modifications que vous avez apportées à l’aide des cmdlets dans les sections précédentes sont appliquées automatiquement au serveur Edge et prennent généralement moins d’une minute pour la réplication. Vous pouvez vérifier l’état de la réplication et que les modifications ont été appliquées à votre serveur Edge à l’aide des applets de commande suivantes.

Pour vérifier les mises à jour de réplication sur un serveur interne dans votre déploiement Lync Server, exécutez l’applet de commande suivante :

    Get-CsManagementStoreReplicationStatus

Pour vérifier que les modifications ont été appliquées, exécutez l’applet de commande suivante sur le serveur Edge :

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Fourniture de la messagerie vocale des utilisateurs de Lync Server 2013 sur la messagerie unifiée Exchange hébergée](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

