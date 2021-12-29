---
title: Utiliser PowerShell pour les tâches dans le menu Surveillance et archivage
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Résumé : Skype Entreprise Server de contrôle au mappage des cmdlet pour le menu Surveillance et archivage.'
ms.openlocfilehash: b286cf1ad1f52e67c4e4171402927c24908aa4ac
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626100"
---
# <a name="monitoring-and-archiving"></a>Surveillance et archivage

Cet article explique comment obtenir des résultats similaires à ceux de l’élément de **menu** Surveillance et archivage du Panneau de contrôle hérité à l’aide d’cmdlets.

Cet article décrit les sous-menus suivants :

- [Surveillance et archivage](#monitoring-and-archiving)
  - [Enregistrement des détails des appels](#call-detail-recording)
  - [Données de qualité de l’expérience](#quality-of-experience-data)
  - [Stratégie d’archivage](#archiving-policy)
  - [Configuration de l’archivage](#archiving-configuration)

## <a name="call-detail-recording"></a>Enregistrement des détails des appels

**Le sous-menu ENREGISTREMENT DES DÉTAILS** DES APPELS permet aux administrateurs de gérer les paramètres d’enregistrement des détails des appels. L’cdr vous permet de suivre l’utilisation de sessions de messagerie instantanée d’égal à égal, d’appels téléphoniques VoIP (Voice over Internet Protocol) et d’appels de conférence.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur l’enregistrement des détails des appels et les cmdlets Skype Entreprise que ces tâches m’indiquent. 

---

> **Scénario 1 :** liste de toutes les configurations d’cdr

   ![Configuration de l’cdr de liste](./media/cdr-configurations-1.png)

***Cmdlet***

[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration)

***Exemple***

```powershell
 Get-CsCdrConfiguration
```

---

> **Scénario 2 :** créer une configuration d’cdr

   ![Créer une configuration cdr](./media/cdr-configurations-2.png)

***Cmdlet***

[New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration)  

***Exemple***

```powershell
 New-CsCdrConfiguration -Identity site:Redmond -EnableCDR $False
```

---

> **Scénario 3 :** obtenir les détails d’une configuration d’cdr choisie

   ![Obtenir la configuration de l’cdr](./media/cdr-configurations-3.png)

***Cmdlet***

[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration)

***Exemple***

```powershell
 Get-CsCdrConfiguration -Identity site:Redmond
```

---

> **Scénario 4 :** Supprimer les configurations d’cdr choisies

   ![Supprimer la configuration de l’cdr](./media/cdr-configurations-4.png)

***Cmdlet***

[Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration)

***Exemple***

```powershell
 Remove-CsCdrConfiguration -Identity site:Redmond
```

---

> **Scénario 5 :** mettre à jour une configuration d’cdr

   ![Mettre à jour la configuration de l’cdr](./media/cdr-configurations-5.png)

***Cmdlet***

[Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration)

***Exemple***

```powershell
 Set-CsCdrConfiguration -Identity site:Redmond -PurgeHourOfDay 23
```

---

## <a name="quality-of-experience-data"></a>Données de qualité de l’expérience

Le **sous-menu DONNÉES QUALITÉ DE L’EXPÉRIENCE** permet aux administrateurs de gérer les paramètres de qualité de l’expérience (QoE). dans l’ensemble de l’organisation ; Cela inclut la gestion du développement de groupes, des paramètres de certificat et des méthodes d’authentification autorisées. Étant donné que les administrateurs peuvent configurer différents paramètres au niveau de l’étendue globale, du site et du service (bien que ce soit le seul service de services Web), vous pouvez personnaliser les fonctionnalités des services Web pour différents utilisateurs et différents emplacements.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur **LE SERVICE WEB** et les cmdlets Skype Entreprise que ces tâches m’indiquent.

---
> **Scénario 1 :** liste de toutes les configurations QoE

   ![Configuration de la QoE de liste](./media/qoe-configuration-1.png)

***Cmdlet***

[Get-CsQoEConfiguration](/powershell/module/skype/get-csqoeconfiguration)

***Exemple***

```powershell
 Get-CsQoEConfiguration
```

---

> **Scénario 2**: créer une configuration QoE

   ![Nouvelle configuration QoE](./media/qoe-configuration-2.png)

***Cmdlet***

[New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration)  

***Exemple***

```powershell
 New-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False
```

---

> **Scénario 3**: obtenir les détails d’une configuration QoE choisie

   ![Obtenir la configuration QoE](./media/qoe-configuration-3.png)

***Cmdlet***

[Get-CsQoEConfiguration](/powershell/module/skype/get-csqoeconfiguration)

***Exemple***

```powershell
 Get-CsQoEConfiguration -Identity site:Redmond
```

---

> **Scénario 4 :** Supprimer les configurations QoE choisies

   ![Supprimer la configuration QoE](./media/qoe-configuration-4.png)

***Cmdlet***

[Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration)

***Exemple***

```powershell
 Remove-CsQoEConfiguration -Identity site:Redmond
```

---

> **Scénario 5 :** mettre à jour une configuration QoE

   ![Mettre à jour la configuration QoE](./media/qoe-configuration-5.png)

***Cmdlet***

[Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration)

***Exemple***

```powershell
 Set-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False
```

---

## <a name="archiving-policy"></a>Stratégie d’archivage

Les administrateurs peuvent utiliser la **STRATÉGIE D’ARCHIVAGE pour** gérer les stratégies d’archivage des sessions de messagerie instantanée. Les stratégies d’archivage vous permettent d’archiver toutes les sessions de messagerie instantanée et de conférence web qui ont lieu entre les utilisateurs internes et/ou entre les utilisateurs internes et les utilisateurs externes

Considérons les différentes tâches qu’un utilisateur peut effectuer sur la STRATÉGIE D’ARCHIVAGE et les cmdlets Skype Entreprise ces tâches. 

---

> **Scénario 1 :** liste de toutes les stratégies d’archivage

   ![Stratégie d’archivage de liste](./media/archiving-policy-1.png)

***Cmdlet***

[Get-CsArchivingPolicy](/powershell/module/skype/get-csarchivingpolicy)

***Exemple***

```powershell
 Get-CsArchivingPolicy
```

---

> **Scénario 2 :** créer une stratégie d’archivage

   ![Créer une stratégie d’archivage](./media/archiving-policy-2.png)

***Cmdlet***

[New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy)  

***Exemple***

```powershell
 New-CsArchivingPolicy -Identity site:Redmond -ArchiveInternal $True
```

---

> **Scénario 3 :** obtenir les détails d’une stratégie d’archivage choisie

   ![Obtenir une stratégie d’archivage](./media/archiving-policy-3.png)

***Cmdlet***

[Get-CsArchivingPolicy](/powershell/module/skype/get-csarchivingpolicy)

***Exemple***

```powershell
 Get-CsArchivingPolicy -Identity site:Redmond
```

---

> **Scénario 4 :** supprimer les stratégies d’archivage choisies

   ![Supprimer une stratégie d’archivage](./media/archiving-policy-4.png)

***Cmdlet***

[Remove-CsArchivingPolicy](/powershell/module/skype/remove-csarchivingpolicy)

***Exemple***

```powershell
 Remove-CsArchivingPolicy -Identity site:Redmond
```

---

> **Scénario 5 :** mettre à jour une stratégie d’archivage

   ![Mettre à jour la stratégie d’archivage](./media/archiving-policy-5.png)

***Cmdlet***

[Set-CsArchivingPolicy](/powershell/module/skype/set-csarchivingpolicy)

***Exemple***

```powershell
 Set-CsArchivingPolicy -Identity global -ArchiveInternal $True
```

---

## <a name="archiving-configuration"></a>Configuration de l’archivage

Les administrateurs peuvent utiliser **la CONFIGURATION D’ARCHIVAGE** pour configurer la façon dont (ou si) les sessions de messagerie instantanée sont archivées dans l’organisation.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur la CONFIGURATION DE **l’ARCHIVAGE** et les Skype Entreprise cmdlets sur Skype Entreprise ces tâches.

---

> **Scénario 1 :** liste de toutes les configurations d’archivage

   ![Configuration de l’archivage de liste](./media/archiving-configuration-1.png)

***Cmdlet***

[Get-CsArchivingConfiguration](/powershell/module/skype/get-csarchivingconfiguration)

***Exemple***

```powershell
 Get-CsArchivingConfiguration
```

---

> **Scénario 2 :** créer une configuration d’archivage

   ![Créer une configuration d’archivage](./media/archiving-configuration-2.png)

***Cmdlet***

[New-CsArchivingConfiguration](/powershell/module/skype/new-csarchivingconfiguration)  

***Exemple***

```powershell
 New-CsArchivingConfiguration -Identity site:Redmond -EnableArchiving "ImOnly"
```

---

> **Scénario 3 :** obtenir les détails d’une configuration d’archivage choisie

   ![Obtenir la configuration de l’archivage](./media/archiving-configuration-3.png)

***Cmdlet***

[Get-CsArchivingConfiguration](/powershell/module/skype/get-csarchivingconfiguration)

***Exemple***

```powershell
 Get-CsArchivingConfiguration -Identity site:Redmond
```

---

> **Scénario 4 :** Supprimer les configurations d’archivage choisies

   ![Supprimer la configuration de l’archivage](./media/archiving-configuration-4.png)

***Cmdlet***

[Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration)

***Exemple***

```powershell
 Remove-CsArchivingConfiguration -Identity site:Redmond
```

---

> **Scénario 5 :** mettre à jour une configuration d’archivage

   ![Mettre à jour la configuration de l’archivage](./media/archiving-configuration-5.png)

***Cmdlet***

[Set-CsArchivingConfiguration](/powershell/module/skype/set-csarchivingconfiguration)

***Exemple***

```powershell
 Set-CsArchivingConfiguration -Identity site:Redmond -ArchiveDuplicateMessages $False -KeepArchivingDataForDays 30
```

---
