---
title: Utiliser PowerShell pour les tâches dans le menu Client
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/12/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Résumé : Skype Entreprise Server panneau de commande au mappage des cmdlet.'
ms.openlocfilehash: e4d72aad28167e3be427f203b8e5b80e2305a636
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60579775"
---
# <a name="client"></a>Client

Cet article décrit comment des résultats similaires à ceux de l’élément de menu **Client** dans le Panneau de contrôle hérité peuvent être obtenus à l’aide d’cmdlets.

Cet article décrit les sous-menus suivants :

- [Client](#client)
  - [Stratégie de version du client](#client-version-policy)
  - [Configuration de version du client](#client-version-configuration)
  - [Mise à jour du périphérique](#device-update)
  - [Périphérique de test](#test-device)
  - [Configuration du fichier journal du périphérique](#device-log-configuration)
  - [Configuration des périphériques](#device-configuration)
  - [Stratégie de mobilité](#mobility-policy)
  - [Configuration des notifications Push](#push-notification-configuration)

## <a name="client-version-policy"></a>Stratégie de version du client

**L’élément de** sous-menu STRATÉGIE DE VERSION DU CLIENT sous le menu **Client** retourne des informations sur les clients pris en charge dans Skype Entreprise Server environnement. Une stratégie de version des clients vous permet de spécifier les clients qui peuvent se Skype Entreprise Server système.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur la STRATÉGIE DE VERSION DU **CLIENT** et les cmdlets Skype Entreprise que ces tâches m’indiquent.

---
> **Scénario 1 :** liste de toutes les stratégies de version des clients

   ![Stratégie de version du client de liste](./media/clientversionpolicy-1.png)

***Cmdlet***

[Get-CsClientVersionPolicy](/powershell/module/skype/get-csclientversionpolicy)

***Exemple***

```powershell
 Get-CsClientVersionPolicy
```

---

> **Scénario 2 :** créer une stratégie de version du client

   ![Nouvelle stratégie de version du client](./media/clientversionpolicy-2.png)

***Cmdlet***

[New-CsClientVersionPolicy](/powershell/module/skype/new-csclientversionpolicy)  

***Exemple***

```powershell
 New-CsClientVersionPolicy -Identity site:Redmond
```

---

> **Scénario 3 :** obtenir les détails d’une stratégie de version du client choisie

   ![Obtenir la stratégie de version du client](./media/clientversionpolicy-3.png)

***Cmdlet***

[Get-CsClientVersionPolicy](/powershell/module/skype/get-csclientversionpolicy)

***Exemple***

```powershell
 Get-CsClientVersionPolicy -Identity site:Redmond
```

---

> **Scénario 4 :** supprimer les stratégies de version des clients choisies

   ![Supprimer la stratégie de version du client](./media/clientversionpolicy-4.png)

***Cmdlet***

[Remove-CsClientVersionPolicy](/powershell/module/skype/remove-csclientversionpolicy)

***Exemple***

```powershell
 Remove-CsClientVersionPolicy -Identity site:Redmond
```

---

> **Scénario 5 :** mettre à jour une stratégie de version du client

   ![Mettre à jour la stratégie de version du client](./media/clientversionpolicy-5.png)

- **Annotation 1 - Résultat**

    Cette annotation sur l’image indique un résultat, c’est-à-dire les données récupérées et affichées.

    ***Cmdlet***

    [Get-CsClientVersionPolicyRule](/powershell/module/skype/get-csclientversionpolicyrule)

    ***Exemple***

    ```powershell
    Get-CsClientVersionPolicyRule -Filter "Global/*"
    ```

- **Annotation 2 - Option (pour l’utilisateur)**

    Cette annotation sur l’image indique une option que l’utilisateur peut implémenter, c’est-à-dire, pour obtenir les détails des règles de stratégie de version du client.

    ***Cmdlet***

    [Get-CsClientVersionPolicyRule](/powershell/module/skype/get-csclientversionpolicyrule)

    ***Exemple***

    ```powershell
    Get-CsClientVersionPolicyRule -Identity "Global/2336c611-a243-4c5d-994b-eea8a524d0e4"
    ```

- **Annotation 3 - Option (pour l’utilisateur)**

    Cette annotation sur l’image indique une option que l’utilisateur peut implémenter, c’est-à-dire, pour créer une règle de stratégie de version du client.

    ***Cmdlet***

    [New-CsClientVersionPolicyRule](/powershell/module/skype/new-csclientversionpolicyrule)

    ***Exemple***

    ```powershell
    $x = \[guid\]::NewGuid()

    New-CsClientVersionPolicyRule -Parent "site:Redmond" -RuleId $x -MajorVersion 4 -UserAgent InHouse
    ```

- **Annotation 4 - Option (pour l’utilisateur)**

    Cette annotation sur l’image indique une option que l’utilisateur peut implémenter, c’est-à-dire pour valider/enregistrer la règle de stratégie de version du client nouvellement créée.

    ***Cmdlet***

    [Set-CsClientVersionPolicy](/powershell/module/skype/set-csclientversionpolicy)

    ***Exemple***

    ```powershell
    Set-CsClientVersionPolicy -Identity site:Redmond -Rules $Null

    $x = Get-CsClientVersionPolicy -Identity site:Dublin | Select-Object -ExpandProperty Rules

    Set-CsClientVersionPolicy -Identity site:Redmond -Rules $x
    ```

---

## <a name="client-version-configuration"></a>Configuration de version du client

 **L’élément de sous-menu CONFIGURATION DE** VERSION DU CLIENT retourne des informations sur les clients pris en charge Skype Entreprise Server’environnement.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur LA **CONFIGURATION DE VERSION** DU CLIENT et les cmdlets Skype Entreprise que ces tâches m’indiquent.

---
> **Scénario 1 :** liste de toutes les configurations de version du client

   ![Configuration de la version du client de liste](./media/ClientVersionConfiguration-1.png)

***Cmdlet***

[Get-CsClientVersionConfiguration](/powershell/module/skype/get-csclientversionconfiguration)

***Exemple***

```powershell
 Get-CsClientVersionConfiguration
```

---

> **Scénario 2 :** créer une configuration de version du client

   ![Créer une configuration de version du client](./media/ClientVersionConfiguration-2.png)

***Cmdlet***

[New-CsClientVersionConfiguration](/powershell/module/skype/new-csclientversionconfiguration)  

***Exemple***

```powershell
 New-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False
```

---

> **Scénario 3 :** obtenir les détails d’une configuration de version de client choisie

   ![Obtenir la configuration de la version du client](./media/ClientVersionConfiguration-3.png)

***Cmdlet***

[Get-CsClientVersionConfiguration](/powershell/module/skype/get-csclientversionconfiguration)

***Exemple***

```powershell
 Get-CsClientVersionConfiguration -Identity site:Redmond
```

---

> **Scénario 4 :** Supprimer les configurations de version du client choisies

   ![Supprimer la configuration de version du client](./media/ClientVersionConfiguration-4.png)

***Cmdlet***

[Remove-CsClientVersionConfiguration](/powershell/module/skype/remove-csclientversionconfiguration)

***Exemple***

```powershell
 Remove-CsClientVersionConfiguration -Identity site:Redmond
```

---

> **Scénario 5 :** mettre à jour une configuration de version du client

   ![Mettre à jour la configuration de la version du client](./media/ClientVersionConfiguration-5.png)

***Cmdlet***

[Set-CsClientVersionConfiguration](/powershell/module/skype/set-csclientversionconfiguration)

***Exemple***

```powershell
Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration -DefaultURL "https://litwareinc.com/csclients"
```

---

> **Scénario 6 :** activer/désactiver les configurations de version du client

![Activer la configuration de la version du client](./media/ClientVersionConfiguration-6.png)

***Cmdlet***

[Set-CsClientVersionConfiguration](/powershell/module/skype/set-csclientversionconfiguration)

***Exemple***

```powershell
Set-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False
```

---

## <a name="device-update"></a>Mise à jour de l’appareil

**Les règles DEVICE UPDATE** sont utilisées pour associer les mises à jour du microprogramme aux appareils qui exécutent Skype Entreprise Téléphone Edition.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur **DEVICE UPDATE** et les cmdlets Skype Entreprise que ces tâches m’indiquent.

---
> **Scénario 1 :** Liste de toutes les mises à jour des périphériques

   ![Liste des mises à jour des périphériques](./media/device-update-1.png)

***Cmdlet***

[Get-CsDeviceUpdateRule](/powershell/module/skype/get-csdeviceupdaterule)

***Exemple***

```powershell
 Get-CsDeviceUpdateRule
```

---

> **Scénario 2 :** supprimer les mises à jour des périphériques

   ![Supprimer la mise à jour des périphériques](./media/device-update-2.png)

***Cmdlet***

[Remove-CsDeviceUpdateRule](/powershell/module/skype/remove-csdeviceupdaterule)  

***Exemple***

```powershell
 Remove-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

> **Scénario 3 :** annuler les mises à jour des périphériques

   ![Annuler la mise à jour de périphérique](./media/device-update-3.png)

***Cmdlet***

[Clear-CsDeviceUpdateFile](/powershell/module/skype/clear-csdeviceupdatefile)

***Exemple***

```powershell
 Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"
```

---

> **Scénario 4 :** approuver les mises à jour des périphériques

   ![Approuver la mise à jour des périphériques](./media/device-update-4.png)

***Cmdlet***

[Approve-CsDeviceUpdateRule](/powershell/module/skype/approve-csdeviceupdaterule)

***Exemple***

```powershell
 Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

> **Scénario 5 : restaurer** les mises à jour des périphériques

   ![Restaurer la mise à jour des périphériques](./media/device-update-5.png)

***Cmdlet***

[Restore-CsDeviceUpdateRule](/powershell/module/skype/restore-csdeviceupdaterule)

***Exemple***

```powershell
 Restore-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

## <a name="test-device"></a>Test d’appareil

L’élément de sous-menu **TEST DEVICE** permet aux administrateurs de tester les mises à jour du microprogramme avant qu’elles ne soient distribuées à tous les périphériques d’une organisation.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur LE **PÉRIPHÉRIQUE DE TEST** et les cmdlets Skype Entreprise que ces tâches m’indiquent.

---
> **Scénario 1 :** Liste de tous les périphériques de test

   ![List Test Device](./media/testdevice-1.png)

***Cmdlet***

[Get-CsTestDevice](/powershell/module/skype/get-cstestdevice)

***Exemple***

```powershell
 Get-CsTestDevice
```

---

> **Scénario 2 :** créer un périphérique de test

   ![Créer un périphérique de test](./media/testdevice-2.png)

***Cmdlet***

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice)  

***Exemple***

```powershell
 New-CsTestDevice -Identity site:Redmond/UCPhone -IdentifierType SerialNumber -Identifier "07823-A345"
```

---

> **Scénario 3 :** obtenir les détails d’un périphérique de test choisi

   ![Obtenir un périphérique de test](./media/testdevice-3.png)

***Cmdlet***

[Get-CsTestDevice](/powershell/module/skype/get-cstestdevice)

***Exemple***

```powershell
 Get-CsTestDevice -Identity site:Redmond/UCPhone
```

---

> **Scénario 4 :** Supprimer les périphériques de test choisis

   ![Supprimer un périphérique de test](./media/testdevice-4.png)

***Cmdlet***

[Remove-CsTestDevice](/powershell/module/skype/remove-cstestdevice)

***Exemple***

```powershell
 Remove-CsTestDevice -Identity site:Redmond
```

---

> **Scénario 5 :** mettre à jour un périphérique de test

   ![Mettre à jour un périphérique de test](./media/testdevice-5.png)

***Cmdlet***

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice)

***Exemple***

```powershell
Set-CsTestDevice -Identity site:Redmond/UCPhone -IdentifierType SerialNumber -Identifier "09768-ABDR-83295"
```

---

## <a name="device-log-configuration"></a>Configuration du fichier journal de l’appareil

L’élément de sous-menu CONFIGURATION DEVICE **LOG** permet de gérer le service Web de mise à jour des périphériques, un composant Skype Entreprise Server qui permet aux administrateurs de distribuer les mises à jour du microprogramme aux téléphones et autres périphériques qui exécutent Skype Entreprise.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur **LA CONFIGURATION** DU JOURNAL DES PÉRIPHÉRIQUEs et les cmdlets Skype Entreprise que ces tâches m’indiquent.

---
> **Scénario 1 :** liste de toutes les configurations du journal des appareils

   ![List Device Log Configuration](./media/device-log-configuration-1.png)

***Cmdlet***

[Get-CsDeviceUpdateConfiguration](/powershell/module/skype/get-csdeviceupdateconfiguration)

***Exemple***

```powershell
 Get-CsDeviceUpdateConfiguration
```

---

> **Scénario 2 :** créer une configuration de journal d’appareil

   ![Créer la configuration des journaux de périphériques](./media/device-log-configuration-2.png)

***Cmdlet***

[New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration)  

***Exemple***

```powershell
 New-CsDeviceUpdateConfiguration -Identity site:Redmond "07823-A345"
```

---

> **Scénario 3 :** obtenir les détails d’une configuration de journal d’appareil choisie

   ![Obtenir la configuration des journaux de périphériques](./media/device-log-configuration-3.png)

***Cmdlet***

[Get-CsDeviceUpdateConfiguration](/powershell/module/skype/get-csdeviceupdateconfiguration)

***Exemple***

```powershell
 Get-CsDeviceUpdateConfiguration -Identity Global
```

---

> **Scénario 4 :** Supprimer les configurations de journal d’appareil choisies

   ![Supprimer la configuration des journaux de périphériques](./media/device-log-configuration-4.png)

***Cmdlet***

[Remove-CsDeviceUpdateConfiguration](/powershell/module/skype/remove-csdeviceupdateconfiguration)

***Exemple***

```powershell
 Remove-CsDeviceUpdateConfiguration -Identity site:Redmond
```

---

> **Scénario 5 : mettre** à jour une configuration de journal d’appareil

   ![Mettre à jour la configuration des journaux de périphériques](./media/device-log-configuration-5.png)

***Cmdlet***

[Set-CsDeviceUpdateConfiguration](/powershell/module/skype/set-csdeviceupdateconfiguration)

***Exemple***

```powershell
Set-CsDeviceUpdateConfiguration -Identity global -MaxLogFileSize 2048000 -MaxLogCacheLimit 1024000
```

---

## <a name="device-configuration"></a>Configuration de l’appareil

**L’élément** de sous-menu CONFIGURATION DE PÉRIPHÉRIQUE permet d’administrer les informations relatives aux options de gestion des téléphones UC. Ces options incluent le mode de sécurité requis et indiquent si le téléphone doit être automatiquement verrouillé après une période d’inactivité spécifiée.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur **LA CONFIGURATION** D’APPAREIL et les cmdlets Skype Entreprise que ces tâches m’indiquent.

---

> **Scénario 1 :** liste de toutes les stratégies de mobilité

   ![List Device Configuration](./media/device-configuration-1.png)

***Cmdlet***

[Get-CsUCPhoneConfiguration](/powershell/module/skype/get-csucphoneconfiguration)

***Exemple***

```powershell
 Get-CsUCPhoneConfiguration
```

---

> **Scénario 2 :** créer une configuration d’appareil

   ![Créer une configuration d’appareil](./media/device-configuration-2.png)

***Cmdlet***

[New-CsUCPhoneConfiguration](/powershell/module/skype/new-csucphoneconfiguration)  

***Exemple***

```powershell
 New-CsUCPhoneConfiguration -Identity site:Redmond -CalendarPollInterval "00:10:00" -LoggingLevel "Medium"
```

---

> **Scénario 3 :** obtenir les détails d’une configuration d’appareil choisie

   ![Obtenir la configuration de l’appareil](./media/device-configuration-3.png)

***Cmdlet***

[Get-CsUCPhoneConfiguration](/powershell/module/skype/get-csucphoneconfiguration)

***Exemple***

```powershell
 Get-CsUCPhoneConfiguration -Identity site:Redmond
```

---

> **Scénario 4 :** supprimer les configurations d’appareil choisies

   ![Supprimer la configuration de l’appareil](./media/device-configuration-4.png)

***Cmdlet***

[Remove-CsUCPhoneConfiguration](/powershell/module/skype/remove-csucphoneconfiguration)

***Exemple***

```powershell
 Remove-CsUCPhoneConfiguration -Identity site:Redmond
```

---

> **Scénario 5 :** met à jour une configuration d’appareil

   ![Mettre à jour la configuration de l’appareil](./media/device-configuration-5.png)

***Cmdlet***

[Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration)

***Exemple***

```powershell
 Set-CsUCPhoneConfiguration -Identity site:Redmond -PhoneLockTimeout "00:30:00"
```

---

## <a name="mobility-policy"></a>Stratégie de mobilité

**LA STRATÉGIE DE** MOBILITÉ détermine si un utilisateur peut utiliser Skype Entreprise Mobile. Elles permettent également à un utilisateur de recourir à la fonctionnalité Appel via le bureau par laquelle ils peuvent passer et recevoir des appels téléphoniques sur leur téléphone mobile à l’aide de leur numéro de téléphone professionnel au lieu de leur numéro de téléphone mobile personnel. Les stratégies de mobilité peuvent également être utilisées pour Wi-Fi connexions requises lors de la prise ou de la réception d’appels.

Prenons en compte les différentes tâches qu’un utilisateur peut effectuer sur **la** STRATÉGIE de mobilité et les Skype Entreprise cmdlets sur Skype Entreprise ces tâches.

---

> **Scénario 1 :** liste de toutes les stratégies de mobilité

   ![Stratégie de mobilité de liste](media/mobility-policy-1.png)

***Cmdlet***

[Get-CsMobilityPolicy](/powershell/module/skype/get-csmobilitypolicy)

***Exemple***

```powershell
 Get-CsMobilityPolicy
```

---

> **Scénario 2 :** créer une stratégie de mobilité

   ![Créer une stratégie de mobilité](./media/mobility-policy-2.png)

***Cmdlet***

[New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy)  

***Exemple***

```powershell
 New-CsMobilityPolicy -Identity site:Redmond -EnableOutsideVoice $False
```

---

> **Scénario 3 :** obtenir les détails d’une stratégie de mobilité choisie

   ![Obtenir une stratégie de mobilité](./media/mobility-policy-3.png)

***Cmdlet***

[Get-CsMobilityPolicy](/powershell/module/skype/get-csmobilitypolicy)

***Exemple***

```powershell
 Get-CsMobilityPolicy -Identity "site:Redmond"
```

---

> **Scénario 4 :** supprimer les stratégies de mobilité choisies

   ![Supprimer la stratégie de mobilité](./media/mobility-policy-4.png)

***Cmdlet***

[Remove-CsMobilityPolicy](/powershell/module/skype/remove-csmobilitypolicy)

***Exemple***

```powershell
 Remove-CsMobilityPolicy -Identity "site:Redmond"
```

---

> **Scénario 5 :** mettre à jour une stratégie de mobilité

   ![Mettre à jour la stratégie de mobilité](./media/mobility-policy-5.png)

***Cmdlet***

[Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy)

***Exemple***

```powershell
Set-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False
```

---

## <a name="push-notification-configuration"></a>Configuration des notifications Push

Le service de notification push (service de notification push Apple et service de notification push de Microsoft) permet d’envoyer des notifications concernant des événements tels que de nouveaux messages instantanés ou de nouveaux messages vocaux à des appareils mobiles tels que des iPhone et des téléphones Windows. Ces notifications sont configurées pour être envoyées même si l’application Skype Entreprise sur ces appareils est actuellement suspendue ou en cours d’exécution en arrière-plan.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur la CONFIGURATION DE **NOTIFICATION PUSH** et les cmdlets Skype Entreprise que ces tâches m’indiquent.

---

> **Scénario 1 :** liste de toutes les stratégies de mobilité

   ![Configuration des notifications Push de liste](./media/push-notification-config-1.png)

***Cmdlet***

[Get-CsPushNotificationConfiguration](/powershell/module/skype/get-cspushnotificationconfiguration)

***Exemple***

```powershell
 Get-CsPushNotificationConfiguration
```

---

> **Scénario 2 :** créer une configuration de notification push

   ![Créer une configuration de notification Push](./media/push-notification-config-2.png)

***Cmdlet***

[New-CsPushNotificationConfiguration](/powershell/module/skype/new-cspushnotificationconfiguration)  

***Exemple***

```powershell
 New-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService -$True
```

---

> **Scénario 3 :** obtenir les détails d’une configuration de notification Push choisie

   ![Obtenir la configuration des notifications Push](./media/push-notification-config-3.png)

***Cmdlet***

[Get-CsPushNotificationConfiguration](/powershell/module/skype/get-cspushnotificationconfiguration)

***Exemple***

```powershell
 Get-CsPushNotificationConfiguration -Identity "site:Redmond"
```

---

> **Scénario 4 :** Supprimer les configurations de notification push choisies

   ![Supprimer la configuration des notifications Push](./media/push-notification-config-4.png)

***Cmdlet***

[Remove-CsPushNotificationConfiguration](/powershell/module/skype/remove-cspushnotificationconfiguration)

***Exemple***

```powershell
 Remove-CsPushNotificationConfiguration -Identity "site:Redmond"
```

---

> **Scénario 5 : mettre** à jour une configuration de notification Push

   ![Mettre à jour la configuration des notifications Push](./media/push-notification-config-5.png)

***Cmdlet***

[Set-CsPushNotificationConfiguration](/powershell/module/skype/set-cspushnotificationconfiguration)

***Exemple***

```powershell
 Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False
```

---
