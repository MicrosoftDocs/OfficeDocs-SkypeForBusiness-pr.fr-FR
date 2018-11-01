---
title: "Lync Server 2013 : Conf. de l’int. de Lync Server local avec Exchange Online"
TOCTitle: Configuration de l’intégration de Lync Server 2013 local avec Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh533880(v=OCS.15)
ms:contentKeyID: 49298127
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de l’intégration de Lync Server 2013 local avec Exchange Online

 

_**Dernière rubrique modifiée :** 2014-07-02_

Les clients qui utilisent des déploiements locaux de Lync Server 2013 peuvent configurer l’interopérabilité avec Microsoft Outlook Web App dans Microsoft Exchange Online dans un mode de déploiement hybride. Les fonctionnalité d’interopérabilité comprennent l’ouverture de session unique et l’intégration de la messagerie instantanée et de la présence avec l’interface d’Outlook Web App. Pour bénéficier de cette intégration, vous devez configurer le serveur Edge dans votre déploiement sur site de Lync Server en effectuant les tâches suivantes :

  - configurer un espace d’adressage SIP partagé ;

  - configurer un fournisseur d’hébergement sur le serveur Edge ;

  - vérifier la réplication du magasin central de gestion mis à jour.

## Configurer un espace d’adressage SIP partagé

Pour intégrer Lync Server 2013 local à Exchange Online, vous devez configurer un espace d’adressage SIP partagé. Le même espace d’adressage SIP est pris en charge par Lync Server et par le service Exchange Online.

À l’aide de Lync Server Management Shell, configurez le serveur Edge pour la fédération en exécutant l’applet de commande **Set-CSAccessEdgeConfiguration** avec les paramètres affichés dans l’exemple suivant :

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - Le paramètre **AllowFederatedUsers** indique si les utilisateurs internes sont autorisés à communiquer avec des utilisateurs de domaines fédérés. Cette propriété détermine également si les utilisateurs internes peuvent communiquer avec des utilisateurs dans un scénario d’espace d’adressage SIP partagé avec Lync Server et Exchange Online.

Pour plus d’informations sur l’utilisation de Lync Server Management Shell, reportez-vous à [Lync Server Management Shell](lync-server-2013-lync-server-management-shell.md).

## Configurer un fournisseur d’hébergement sur le serveur Edge.

À l’aide de Lync Server Management Shell, configurez un fournisseur d’hébergement sur le serveur Edge en exécutant l’applet de commande **New-CsHostingProvider** avec les paramètres de l’exemple suivant :

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

> [!NOTE]  
> Si vous utilisez Office 365 activé par 21Vianet en Chine, remplacez dans cet exemple la valeur du paramètre <strong>ProxyFqdn</strong> (« exap.um.outlook.com ») par le FQDN du service activé par 21Vianet: « exap.um.partner.outlook.cn ».

  - **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez (par exemple, « Exchange Online »). Les valeurs qui contiennent des espaces doivent être placées entre guillemets doubles.

  - **Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Ce paramètre doit avoir la valeur True.

  - **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adressage SIP partagé. Ce paramètre doit avoir la valeur True.

  - **HostsOCSUsers** indique si le fournisseur d’hébergement sert à héberger Office Communications Server ou Lync Server. Ce paramètre doit avoir la valeur False.

  - **ProxyFQDN** spécifie le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement. Pour Exchange Online, le nom de domaine complet est exap.um.outlook.com.

  - **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Lync Server. Ce paramètre doit avoir la valeur False.

  - **VerificationLevel** indique le niveau de vérification autorisé pour les messages à destination et en provenance du fournisseur hébergé. Spécifiez **UseSourceVerification**, qui repose sur le niveau de vérification inclus dans les messages en provenance du fournisseur hébergé. Si ce niveau n’est pas spécifié, le message est rejeté comme message non vérifiable.

## Vérifier la réplication du magasin central de gestion mis à jour

Les modifications que vous avez apportées à l’aide des applets de commande dans les sections précédentes sont appliquées automatiquement au serveur Edge et leur réplication prend généralement moins d’une minute. Vous pouvez valider l’état de la réplication, puis confirmer que les modifications ont été appliquées à votre serveur Edge au moyen des applets de commande suivantes :

Pour vérifier les mises à jour de réplication, sur un serveur interne dans votre déploiement de Lync Server, exécutez l’applet de commande suivante :

    Get-CsManagementStoreReplicationStatus

Pour confirmer que les modifications ont été appliquées, sur le serveur Edge, exécutez l’applet de commande suivante :

    Get-CsHostingProvider -LocalStore

## Voir aussi

#### Autres ressources

[Mise à disposition de la messagerie vocale Lync Server 2013 aux utilisateurs sur la messagerie unifiée Exchange hébergée](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md)

