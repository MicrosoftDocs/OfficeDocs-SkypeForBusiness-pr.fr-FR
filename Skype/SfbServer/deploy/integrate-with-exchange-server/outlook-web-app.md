---
title: Configurer l’intégration entre l’application Skype Entreprise Server locale et Outlook Web App
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Résumé : Intégrez Skype Entreprise Server et Outlook Web App.'
ms.openlocfilehash: 9555303ad5bcb3ad15702f0cf1768549330e33cd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60738860"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Configurer l’intégration entre l’application Skype Entreprise Server locale et Outlook Web App

**Résumé :** Intégrez Skype Entreprise Server et Outlook Web App.

Les clients qui utilisent des déploiements locaux Skype Entreprise Server peuvent configurer l’interopérabilité avec Microsoft Outlook Web App dans Microsoft Exchange Online dans un mode de déploiement hybride. Les fonctionnalités d’interopérabilité comprennent l’ouverture de session unique et l’intégration de la messagerie instantanée et de la présence avec l’interface d’Outlook Web App. Pour activer cette intégration, vous devez configurer le serveur Edge dans votre déploiement Skype Entreprise Server local en effectuant les tâches suivantes :

- configurer un espace d’adressage SIP partagé ;

- Configurer un fournisseur d’hébergement sur le serveur Edge

- Vérifier la réplication du magasin central de gestion mis à jour

## <a name="configure-a-shared-sip-address-space"></a>Configurer un espace d’adressage SIP partagé

Pour intégrer des Skype Entreprise Server avec Exchange Online, vous devez configurer un espace d’adressaie SIP partagé. Le même espace d’adressan de domaine SIP est pris en charge par Skype Entreprise Server et le service Exchange Online client.

À l’aide de Skype Entreprise Server Management Shell, configurez le serveur Edge pour la fédération en exécutant l’cmdlet **Set-CSAccessEdgeConfiguration,** à l’aide des paramètres affichés dans l’exemple suivant :

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- Le paramètre **AllowFederatedUsers** indique si les utilisateurs internes sont autorisés à communiquer avec des utilisateurs de domaines fédérés. Cette propriété détermine également si les utilisateurs internes peuvent communiquer avec des utilisateurs dans un scénario d’espace d’adressas SIP partagé avec Skype Entreprise Server et Exchange Online.

Pour plus d’informations sur l’utilisation Skype Entreprise Server Management Shell, voir [Skype Entreprise Server Management Shell.](../../manage/management-shell.md)

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurer un fournisseur d’hébergement sur le serveur Edge.

À l’aide de Skype Entreprise Server Management Shell, configurez un fournisseur d’hébergement sur le serveur Edge en exécutant l’cmdlet **New-CsHostingProvider,** en utilisant les paramètres de l’exemple suivant :

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Si vous utilisez Microsoft 365 ou Office 365 géré par 21Vianet en Chine, remplacez la valeur du paramètre ProxyFqdn dans cet exemple (« exap.um.outlook.com ») par le FQDN du service géré par 21Vianet : « exap.um.partner.outlook.cn ». Si vous utilisez Microsoft 365 ou Office 365 Cloud de la communauté du secteur public High, remplacez la valeur du paramètre ProxyFqdn dans cet exemple (« exap.um.outlook.com ») par le FQDN pour Cloud de la communauté du secteur public High : « exap.um.office365.us ».

- **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez (par exemple, « Exchange Online »). Les valeurs qui contiennent des espaces doivent être placées entre guillemets doubles.

- **Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Ce paramètre doit avoir la valeur True.

- **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adressage SIP partagé. Ce paramètre doit avoir la valeur True.

- **HostsOCSUsers indique** si le fournisseur d’hébergement est utilisé pour héberger Office Communications Server ou Skype Entreprise Server. Ce paramètre doit avoir la valeur False.

- **ProxyFQDN** spécifie le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement. Pour Exchange Online, le nom de domaine complet est exap.um.outlook.com.

- **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans Skype Entreprise Server topologie. Ce paramètre doit avoir la valeur False.

- **VerificationLevel** Indique le niveau de vérification autorisé pour les messages envoyés vers et depuis le fournisseur hébergé. Spécifiez **UseSourceVerification**, qui s’appuie sur le niveau de vérification inclus dans les messages envoyés par le fournisseur d’hébergement. Si ce niveau n’est pas spécifié, le message est rejeté comme étant non vérifiable.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Vérifier la réplication du magasin central de gestion mis à jour

Les modifications que vous avez apportées à l’aide des cmdlets des sections précédentes sont automatiquement appliquées au serveur Edge et prennent généralement moins d’une minute pour être répliquées. Vous pouvez valider l’état de la réplication, puis confirmer que les modifications ont été appliquées à votre serveur Edge à l’aide des cmdlets suivantes.

Pour vérifier les mises à jour de réplication, sur un serveur interne dans votre déploiement Skype Entreprise Server, exécutez l’cmdlet suivante :

```powershell
Get-CsManagementStoreReplicationStatus
```
Vérifiez si la valeur UpToDate affiche TRUE pour tous les réplicas.

Pour confirmer que les modifications ont été appliquées, sur le serveur Edge, exécutez l’cmdlet suivante :

```powershell
Get-CsHostingProvider -LocalStore
```
Vérifiez si les informations affichées sont en correspondance avec les modifications apportées aux étapes précédentes.

## <a name="see-also"></a>Voir aussi

[Fourniture de Skype Entreprise Server messagerie vocale aux utilisateurs sur une messagerie Exchange hébergée](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)

[Intégration de Exchange messagerie unifiée hébergée dans Skype Entreprise Server](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)