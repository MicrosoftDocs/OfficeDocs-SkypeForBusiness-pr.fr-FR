---
title: Configurer l’intégration entre Skype entreprise Server local et Outlook Web App
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Résumé : intégrez Skype entreprise Server et Outlook Web App.'
ms.openlocfilehash: ee5676c0dbe88568af78a1c278eea8a46457cb5c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221184"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Configurer l’intégration entre Skype entreprise Server local et Outlook Web App

**Résumé :** Intégrez Skype entreprise Server et Outlook Web App.

Les clients qui utilisent des déploiements Skype entreprise Server sur site peuvent configurer l’interopérabilité avec Microsoft Outlook Web App dans Microsoft Exchange Online dans un mode de déploiement hybride. Les fonctionnalités d’interopérabilité comprennent l’ouverture de session unique et l’intégration de la messagerie instantanée et de la présence avec l’interface d’Outlook Web App. Pour activer cette intégration, vous devez configurer le serveur Edge dans votre déploiement Skype entreprise Server sur site en effectuant les tâches suivantes :

- configurer un espace d’adressage SIP partagé ;

- Configurer un fournisseur d’hébergement sur le serveur Edge

- Vérifier la réplication du magasin central de gestion mis à jour

## <a name="configure-a-shared-sip-address-space"></a>Configurer un espace d’adressage SIP partagé

Pour intégrer Skype entreprise Server sur site à Exchange Online, vous devez configurer un espace d’adressage SIP partagé. Le même espace d’adressage de domaine SIP est pris en charge par Skype entreprise Server et le service Exchange Online.

À l’aide de Skype entreprise Server Management Shell, configurez le serveur Edge pour la Fédération en exécutant la cmdlet **Set-CSAccessEdgeConfiguration** à l’aide des paramètres affichés dans l’exemple suivant :

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- Le paramètre **AllowFederatedUsers** indique si les utilisateurs internes sont autorisés à communiquer avec des utilisateurs de domaines fédérés. Cette propriété détermine également si les utilisateurs internes peuvent communiquer avec des utilisateurs dans un scénario d’espace d’adressage SIP partagé avec Skype entreprise Server et Exchange Online.

Pour plus d’informations sur l’utilisation de Skype entreprise Server Management Shell, voir [Skype for Business Server Management Shell](../../manage/management-shell.md).

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurer un fournisseur d’hébergement sur le serveur Edge.

À l’aide de Skype entreprise Server Management Shell, configurez un fournisseur d’hébergement sur le serveur Edge en exécutant la cmdlet **New-CsHostingProvider** à l’aide des paramètres de l’exemple suivant :

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Si vous utilisez Microsoft 365 ou Office 365 géré par 21Vianet en Chine, remplacez la valeur du paramètre ProxyFqdn dans cet exemple ("exap.um.outlook.com") par le nom de domaine complet (FQDN) du service géré par 21Vianet : "exap.um.partner.outlook.cn". Si vous utilisez Microsoft 365 ou Office 365 GCC High, remplacez la valeur du paramètre ProxyFqdn dans cet exemple ("exap.um.outlook.com") par le nom de domaine complet (FQDN) de GCC High : "exap.um.office365.us".

- **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez (par exemple, « Exchange Online »). Les valeurs qui contiennent des espaces doivent être placées entre guillemets doubles.

- **Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Ce paramètre doit avoir la valeur True.

- **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adressage SIP partagé. Ce paramètre doit avoir la valeur True.

- **HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger Office Communications Server ou Skype entreprise Server. Ce paramètre doit avoir la valeur False.

- **ProxyFQDN** spécifie le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement. Pour Exchange Online, le nom de domaine complet est exap.um.outlook.com.

- **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Skype entreprise Server. Ce paramètre doit avoir la valeur False.

- **VerificationLevel** Indique le niveau de vérification autorisé pour les messages échangés avec le fournisseur hébergé. Spécifiez **UseSourceVerification**, qui s’appuie sur le niveau de vérification inclus dans les messages envoyés par le fournisseur d’hébergement. Si ce niveau n’est pas spécifié, le message sera rejeté comme non vérifiable.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Vérifier la réplication du magasin central de gestion mis à jour

Les modifications que vous avez apportées à l’aide des applets de commande dans les sections précédentes sont appliquées automatiquement au serveur Edge et prennent généralement moins d’une minute à répliquer. Vous pouvez valider l’état de la réplication, puis confirmer que les modifications ont été appliquées à votre serveur Edge à l’aide des applets de commande suivantes.

Pour vérifier les mises à jour de réplication, sur un serveur interne dans votre déploiement de Skype entreprise Server, exécutez l’applet de commande suivante :

```powershell
Get-CsManagementStoreReplicationStatus
```
Vérifiez si la valeur UpToDate indique TRUE pour tous les réplicas.

Pour confirmer que les modifications ont été appliquées, sur le serveur Edge, exécutez l’applet de commande suivante :

```powershell
Get-CsHostingProvider -LocalStore
```
Double vérifier si les informations indiquées correspondent aux modifications validées lors des étapes précédentes.

## <a name="see-also"></a>Voir aussi

[Fourniture de la messagerie vocale des utilisateurs de Skype entreprise Server sur la messagerie unifiée Exchange hébergée](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[Intégration de la messagerie unifiée Exchange hébergée dans Skype entreprise Server](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
