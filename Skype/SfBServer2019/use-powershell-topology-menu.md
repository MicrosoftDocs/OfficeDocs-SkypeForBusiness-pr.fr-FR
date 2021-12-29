---
title: Utiliser PowerShell pour les tâches dans le menu Topologie
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
description: 'Résumé : Skype Entreprise Server de commande au mappage des cmdlet pour le menu Topologie.'
ms.openlocfilehash: da5374863d7b9e7c8217802ce98e10cfdab92e54
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626099"
---
# <a name="topology"></a>Topologie

Cet article décrit comment des résultats similaires à ceux de l’élément de **menu** Topologie dans le Panneau de contrôle hérité peuvent être obtenus à l’aide d’cmdlets.

Cet article décrit les sous-menus suivants :

- [Topologie](#topology)
  - [État](#status)
  - [Application serveur](#server-application)
  - [URL simple](#simple-url)
  - [Application fiable](#trusted-application)

## <a name="status"></a>Statut

**Le** sous-menu STATUS permet aux administrateurs de gérer les ordinateurs de la topologie.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur **STATUS** et les cmdlets Skype Entreprise que ces tâches m’indiquent.

---

> **Scénario 1 :** liste de tous les ordinateurs et de leur état

   ![Ordinateur de liste et état](./media/topology-status-1.png)

   ***Cmdlet***

   [Get-CsPool](/powershell/module/skype/get-cspool)

   ***Exemple***

   ```powershell
    Get-CsPool
   ```

   ***Cmdlet***

   [Get-CsComputer](/powershell/module/skype/get-cscomputer)

   ***Exemple***

   ```powershell
    Get-CsComputer
   ```

   ***Cmdlet***

   [Get-CsManagementStoreReplicationStatus](/powershell/module/skype/get-csmanagementstorereplicationstatus)

   ***Exemple***

   ```powershell
   Get-CsManagementStoreReplicationStatus
   ```

---

## <a name="server-application"></a>Application serveur

Les applications serveur font référence aux programmes individuels qui s’exécutent sous Skype Entreprise Server. **Le** sous-menu SERVER APPLICATION permet aux administrateurs de retourner des informations sur une (ou toutes) des applications en cours d’exécution dans le cadre de Skype Entreprise Server.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur **SERVER APPLICATION** et les cmdlets Skype Entreprise que ces tâches m’indiquent.

---
> **Scénario 1 :** Liste de toutes les applications serveur

   ![List Server Application](./media/server-application-1.png)

***Cmdlet***

[Get-CsServerApplication](/powershell/module/skype/get-csserverapplication)

***Exemple***

```powershell
 Get-CsServerApplication
```

---

> **Scénario 2 :** activer/désactiver ou sélectionner critique/désélectionner une application serveur critique

   ![Modifier l’application serveur](./media/server-application-2.png)

***Cmdlet***

[Set-CsServerApplication](/powershell/module/skype/get-csserverapplication)

***Exemple***

```powershell
 Set-CsServerApplication -Identity "Registrar:atl-cs-001.litwareinc.com/ExumRouting" -Enabled $True
```

---

## <a name="simple-url"></a>URL simple

Les URL simples permettent aux utilisateurs de rejoindre plus facilement des réunions et des conférences, et aux administrateurs de se connecter plus facilement au Panneau de Skype Entreprise Server. Le sous-menu **URL simple** permet aux administrateurs de les afficher.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur **l’URL simple** et les Skype Entreprise que ces tâches m’indiquent.

---
> **Scénario 1 :** Liste de toutes les configurations d’URL simples

   ![URL simple de liste](./media/simple-url-1.png)

***Cmdlet***

[Get-CsSimpleUrlConfiguration](/powershell/module/skype/get-cssimpleurlconfiguration)

***Exemple***

```powershell
 Get-CsSimpleUrlConfiguration | Select-Object -ExpandProperty SimpleUrl
```

---

## <a name="trusted-application"></a>Application fiable

Une application fiable est une application développée par un tiers qui a le statut approuvé pour s’exécuter dans le cadre de Skype Entreprise Server mais qui n’est pas une partie intégrée du produit. Le **sous-menu APPLICATION** APPROUVÉ permet à l’administrateur de les afficher.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur **TRUSTED APPLICATION** et les cmdlets Skype Entreprise que ces tâches m’indiquent.

---
> **Scénario 1 :** Liste de toutes les applications fiables

   ![List Trusted Application](./media/trusted-application-1.png)

***Cmdlet***

[Get-CsTrustedApplication](/powershell/module/skype/get-cstrustedapplication)

***Exemple***

```powershell
 Get-CsTrustedApplication
```

---
