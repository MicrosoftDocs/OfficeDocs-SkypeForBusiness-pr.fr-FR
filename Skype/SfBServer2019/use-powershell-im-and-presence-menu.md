---
title: Utiliser PowerShell pour les tâches dans le menu Messagerie instantanée et présence
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
description: 'Résumé : Skype Entreprise Server de contrôle au mappage des cmdlet pour le menu de messagerie instantanée et de présence.'
ms.openlocfilehash: 9d57e249fb839894454c05d25e78320153d4a306
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2021
ms.locfileid: "60888754"
---
# <a name="im-and-presence"></a>Messagerie instantanée et présence

Cet article décrit comment des résultats similaires à ceux de l’élément de **menu** de messagerie instantanée et de présence dans le Panneau de contrôle hérité peuvent être obtenus à l’aide d’cmdlets.

Cet article décrit les sous-menus suivants :

- [Messagerie instantanée et présence](#im-and-presence)
  - [Filtre de fichier](#file-filter)
  - [Filtre d’URL](#url-filter)

## <a name="file-filter"></a>Filtre de fichier

**Le sous-menu FILE FILTER** permet aux administrateurs de gérer les configurations de filtre de transfert de fichiers dans l’organisation. Ces configurations sont utilisées pour bloquer la capacité d’un utilisateur à transférer certains types de fichiers (par exemple, les fichiers avec une extension de fichier .vbs ou .ps1) à l’aide d’un client Skype Entreprise Server.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur **FILE FILTER** et les cmdlets Skype Entreprise que ces tâches maient.

---

> **Scénario 1 :** liste de tous les filtres de fichiers

   ![Filtre de fichier de liste](./media/file-filter-1.png)

***Cmdlet***

[Get-CsFileTransferFilterConfiguration](/powershell/module/skype/get-csfiletransferfilterconfiguration)

***Exemple***

```powershell
 Get-CsFileTransferFilterConfiguration
```

---

> **Scénario 2 :** créer un filtre de fichiers

   ![Créer un filtre de fichier](./media/file-filter-2.png)

***Cmdlet***

[New-CsFileTransferFilterConfiguration](/powershell/module/skype/new-csfiletransferfilterconfiguration)  

***Exemple***

```powershell
 New-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **Scénario 3 :** obtenir les détails d’un filtre de fichier choisi

   ![Obtenir un filtre de fichier](./media/file-filter-3.png)

***Cmdlet***

[Get-CsFileTransferFilterConfiguration](/powershell/module/skype/get-csfiletransferfilterconfiguration)

***Exemple***

```powershell
 Get-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **Scénario 4 :** supprimer les filtres de fichiers choisis

   ![Supprimer le filtre de fichiers](./media/file-filter-4.png)

***Cmdlet***

[Remove-CsFileTransferFilterConfiguration](/powershell/module/skype/remove-csfiletransferfilterconfiguration)

***Exemple***

```powershell
 Remove-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **Scénario 5 :** mettre à jour un filtre de fichier

   ![Mettre à jour le filtre de fichier](./media/file-filter-5.png)

***Cmdlet***

[Set-CsFileTransferFilterConfiguration](/powershell/module/skype/set-csfiletransferfilterconfiguration)

***Exemple***

```powershell
 Set-CsFileTransferFilterConfiguration -Identity site:Redmond -Extensions @{Add=".ps1"}
```

---

## <a name="url-filter"></a>Filtre d’URL

L’élément de sous-menu FILTRE d’URL sous MESSAGERIE INSTANTANÉE et présence permet aux administrateurs de configurer le filtre d’URL afin que les liens hypertexte avec certains préfixes soient bloqués ou ne soient pas actifs.   (En d’autres termes, les participants ne peuvent pas simplement cliquer sur le lien et se rendre sur le site référent par l’URI ; ils doivent copier et coller le lien manuellement dans un navigateur.)

Considérons les différentes tâches qu’un utilisateur peut effectuer sur LE FILTRE **d’URL** et les cmdlets Skype Entreprise que ces tâches maient.

---
> **Scénario 1 :** Liste de tous les filtres d’URL web

   ![Filtre d’URL de liste](./media/url-filter-1.png)

***Cmdlet***

[Get-CsImFilterConfiguration](/powershell/module/skype/get-csimfilterconfiguration)

***Exemple***

```powershell
 Get-CsImFilterConfiguration
```

---

> **Scénario 2 :** créer un filtre d’URL

   ![Nouveau filtre d’URL](./media/url-filter-2.png)

***Cmdlet***

[New-CsImFilterConfiguration](/powershell/module/skype/new-csimfilterconfiguration)  

***Exemple***

```powershell
 New-CsImFilterConfiguration -Identity site:Redmond
```

---

> **Scénario 3 :** obtenir les détails d’un filtre d’URL choisi

   ![Obtenir un filtre d’URL](./media/url-filter-3.png)

***Cmdlet***

[Get-CsImFilterConfiguration](/powershell/module/skype/get-csimfilterconfiguration)

***Exemple***

```powershell
 Get-CsImFilterConfiguration -Identity site:Redmond
```

---

> **Scénario 4 :** Supprimer les filtres d’URL choisis

   ![Supprimer un filtre d’URL](./media/url-filter-4.png)

***Cmdlet***

[Remove-CsImFilterConfiguration](/powershell/module/skype/remove-csimfilterconfiguration)

***Exemple***

```powershell
 Remove-CsImFilterConfiguration -Identity site:Redmond
```

---

> **Scénario 5 : mettre** à jour un filtre d’URL

   ![Mettre à jour le filtre d’URL](./media/url-filter-5.png)

***Cmdlet***

[Set-CsImFilterConfiguration](/powershell/module/skype/set-csimfilterconfiguration)

***Exemple***

```powershell
 Set-CsImFilterConfiguration -Identity site:Redmond -Enabled $False
```

---
