---
title: Mise à jour de la liste d’activation Outlook
TOCTitle: Mise à jour de la liste d’activation Outlook
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ215438(v=OCS.15)
ms:contentKeyID: 49297354
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mise à jour de la liste d’activation Outlook

 

_**Dernière rubrique modifiée :** 2013-01-07_

Pour vous assurer que le complément de réunion en ligne pour Microsoft Lync 2013 est toujours activé pour les utilisateurs, vous pouvez créer une stratégie qui inclut ce complément dans la liste de gestion des compléments pour Outlook. La stratégie Liste de gestion des compléments est incluse dans les fichiers de modèle d’administration Office pour la Console de gestion des stratégies de groupe. Elle crée une clé de Registre sous HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList. Vous pouvez ajouter une valeur à cette clé pour la bibliothèque de liens dynamiques ucaddin.dll et configurer la valeur ucaddin.dll afin qu’elle soit toujours activée et que les utilisateurs ne puissent pas la désactiver manuellement.

## Pour ajouter ucaddin.dll à la liste des compléments Outlook

  - À la clé de Registre AddinList, située sous HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList, ajoutez la valeur suivante :
    
      - Type de Registre = REG\_SZ
    
      - Nom = ucaddin.dll
    
      - Valeur = 1 (spécifie que le complément est toujours activé et qu’il ne peut pas être géré par l’utilisateur final)

