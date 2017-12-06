---
title: "Conserver les fichiers volumineux joints à un Skype entreprise"
ms.author: tonysmit
author: tonysmit
ms.date: 11/7/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
description: "Vous pouvez joindre des fichiers à une réunion Skype Entreprise, les participants peuvent ensuite ouvrir et téléchargement. Fichiers joints aux réunions Skype Entreprise sont conservés dans les boîtes aux lettres d'un participant dont boîte aux lettres est placé sur litige maintenez la touche, comporte une stratégie de rétention Office 365 ou est placé sur une suspension associée à un cas eDiscovery dans le Centre de sécurité et conformité Office 365. Ce contenu est enregistré dans les dossiers d'Éléments récupérables des participants dans leur boîte aux lettres."
---

# Conserver les fichiers volumineux joints à un Skype entreprise

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](12203a1a-4a9f-4838-88c5-3740ea16ed8d.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/12203a1a-4a9f-4838-88c5-3740ea16ed8d). 
  
Vous pouvez joindre des fichiers à une réunion Skype Entreprise, les participants peuvent ensuite ouvrir et téléchargement. Fichiers joints aux réunions Skype Entreprise sont conservés dans les boîtes aux lettres d'un participant dont boîte aux lettres est placé sur litige maintenez la touche, comporte une stratégie de rétention Office 365 ou est placé sur une suspension associée à un cas eDiscovery dans le Centre de sécurité et conformité Office 365. Ce contenu est enregistré dans les dossiers **d'Éléments récupérables** des participants dans leur boîte aux lettres.
  
Les fichiers qui sont conservés dans les boîtes aux lettres en attente sont indexés et par conséquent peuvent être recherchés lors de l'exécution d'une recherche de contenu dans les Centre de sécurité et conformité lors de la recherche de boîte aux lettres d'un participant. Toutefois, les fichiers joints qui sont supérieures à 39 Mo sont Fractionner en deux ou plusieurs fichiers plus petits et enregistrement en tant que fichiers compressés (.zip). Le  *contenu*  de ces fichiers de petite taille n'est pas indexé pour la recherche et ne peut pas être retourné dans une recherche de contenu. Toutefois, les *métadonnées*  de ces fichiers (par exemple, le nom de fichier et l'auteur) sont indexé pour la recherche et peuvent être renvoyés dans une recherche de contenu.
  
> [!NOTE]
> Si la boîte aux lettres est pleine ou l'administrateur client a configuré MaxSendSize est inférieure à 39 Mo, téléchargés fichier de données ne sont pas conservées du tout. La valeur par défaut MaxSendSize est de 150 Mo, mais les administrateurs client peuvent configurer MaxSendSize pour soit aussi petite que 1 Mo. 
  
Boîtes aux lettres qui ne sont pas en attente n'ont pas toutes les données réunion enregistrées. Par exemple, dans une réunion de trois personnes dans lequel les boîtes aux lettres de deux participants sont marqués pour la rétention, les données de la réunion sont enregistrées dans les boîtes aux lettres de ces deux participants, mais pas à la boîte aux lettres du participant tiers, dont boîte aux lettres n'est pas sur Maintenez la touche.
  
## Voir aussi

[Exécuter une recherche de contenu dans le centre de conformité &amp; sécurité Office 365](https://support.office.com/article/61852fd9-fe8a-4880-a339-cb19ed3bff4a .aspx)
  
[Éléments non indexés dans recherche de contenu dans Office 365](https://support.office.com/article/d1691de4-ca0d-446f-a0d0-373a4fc8487b)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

