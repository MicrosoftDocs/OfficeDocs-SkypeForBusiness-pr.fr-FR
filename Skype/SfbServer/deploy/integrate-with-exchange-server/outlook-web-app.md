---
title: Configurer l’intégration entre Skype entreprise Server et Outlook Web App
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
ms.openlocfilehash: 2496cc7c2f357c4e1afa73dea18f304c6a7f9607
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797035"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Configurer l’intégration entre Skype entreprise Server et Outlook Web App

**Résumé :** Intégrez Skype entreprise Server et Outlook Web App.

Les clients utilisant un déploiement local de Skype entreprise Server peuvent configurer l’interopérabilité avec Microsoft Outlook Web App dans Microsoft Exchange Online dans un mode de déploiement hybride. Les fonctionnalités d’interopérabilité comprennent l’ouverture de session unique, l’intégration de la messagerie instantanée et de la présence dans l’interface d’Outlook Web App. Pour activer cette intégration, vous devez configurer le serveur de périphérie dans votre déploiement de Skype entreprise Server sur site en effectuant les tâches suivantes :

- configurer un espace d’adressage SIP partagé ;

- Configurer un fournisseur d’hébergement sur le serveur Edge

- Vérification de la réplication du magasin central de gestion mis à jour

## <a name="configure-a-shared-sip-address-space"></a>Configurer un espace d’adressage SIP partagé

Pour intégrer Skype entreprise Server sur site à Exchange Online, vous devez configurer un espace d’adressage SIP partagé. Le même espace d’adresse de domaine SIP est pris en charge par Skype entreprise Server et le service Exchange Online.

À l’aide de Skype entreprise Server Management Shell, configurez le serveur Edge pour la Fédération en exécutant l’applet de commande **Set-CSAccessEdgeConfiguration** en utilisant les paramètres présentés dans l’exemple suivant :

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- Le paramètre **AllowFederatedUsers** indique si les utilisateurs internes sont autorisés à communiquer avec des utilisateurs de domaines fédérés. Cette propriété détermine également si les utilisateurs internes peuvent communiquer avec des utilisateurs dans un scénario d’espace d’adressage SIP partagé avec Skype entreprise Server et Exchange Online.

Pour plus d’informations sur l’utilisation de Skype entreprise Server Management Shell, reportez-vous à la rubrique [Skype entreprise Server Management Shell](../../manage/management-shell.md).

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurer un fournisseur d’hébergement sur le serveur Edge.

À l’aide de Skype entreprise Server Management Shell, configurez un fournisseur d’hébergement sur le serveur Edge en exécutant l’applet **de commande New-CsHostingProvider** en utilisant les paramètres dans l’exemple suivant :

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Si vous utilisez Office 365 activé par 21Vianet en Chine, remplacez dans cet exemple la valeur du paramètre ProxyFqdn (« exap.um.outlook.com ») par le FQDN du service activé par 21Vianet: « exap.um.partner.outlook.cn ». Si vous utilisez la fonction de haut-parleurs d’Office 365, remplacez la valeur du paramètre ProxyFqdn dans cet exemple (« exap.um.outlook.com ») par le nom de domaine complet (« exap.um.office365.us »).

- **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez (par exemple, « Exchange Online »). Les valeurs qui contiennent des espaces doivent être placées entre guillemets doubles.

- **Enabled ** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Ce paramètre doit avoir la valeur True.

- **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adressage SIP partagé. Ce paramètre doit avoir la valeur True.

- **HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger Office Communications Server ou Skype entreprise Server. Ce paramètre doit avoir la valeur False.

- **ProxyFQDN** spécifie le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement. Pour Exchange Online, le nom de domaine complet est exap.um.outlook.com.

- **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie de Skype entreprise Server. Ce paramètre doit avoir la valeur False.

- **VerificationLevel** Indique le niveau de vérification autorisé pour les messages échangés avec le fournisseur hébergé. Spécifiez **UseSourceVerification**, qui repose sur le niveau de vérification inclus dans les messages en provenance du fournisseur hébergé. Si ce niveau n’est pas spécifié, le message est rejeté comme invérifiable.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Vérifier la réplication du magasin central de gestion mis à jour

Les modifications que vous avez apportées à l’aide des applets de passe dans les sections précédentes s’appliquent automatiquement au serveur Edge et prennent généralement moins d’une minute de réplication. Vous pouvez valider l’état de la réplication, puis vérifier qu’elles ont été appliquées à votre serveur Edge en utilisant les applets de commande suivantes.

Pour vérifier les mises à jour de réplication, sur un serveur interne à votre déploiement de Skype entreprise Server, exécutez l’applet de commande suivante :

```powershell
Get-CsManagementStoreReplicationStatus
```
Vérifiez si la valeur UpToDate s’affiche TRUE pour tous les réplicas.

Pour confirmer l’application des modifications, sur le serveur Edge, exécutez l’applet de commande suivante :

```powershell
Get-CsHostingProvider -LocalStore
```
Vérifiez si les informations affichées correspondent aux modifications validées au cours des étapes précédentes.

## <a name="see-also"></a>Voir aussi

[Fourniture de messages vocaux aux utilisateurs de Skype entreprise Server sur la messagerie unifiée Exchange hébergée](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[Intégration de la messagerie unifiée Exchange hébergée dans Skype entreprise Server](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
