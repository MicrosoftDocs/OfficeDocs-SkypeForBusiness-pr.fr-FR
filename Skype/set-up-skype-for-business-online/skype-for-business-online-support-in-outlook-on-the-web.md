---
title: Prise en charge de Skype Entreprise Online avec Outlook sur le Web
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Outlook sur le web (Outlook Web App) dans Office 365 propose une base Skype pour client web Business à partir de la barre de navigation. Ce client de base est disponible pour les utilisateurs en ligne dont admin n’a pas configuré une URL vanity pour leur organisation d’Office 365. Tant que le compte d’utilisateur est en ligne et n’a pas une URL de courtoisie, ils pourront toujours voir l’expérience même si leur organisation a certains comptes d’utilisateurs qui sont hébergées sur site. Les utilisateurs qui ont des utilisateurs comptes locaux (qu’ils aient une URL vanity ou non) ou sont gérés par Microsoft verront l’expérience Lync dans Outlook web app."
ms.openlocfilehash: 8688123f0e19a648dae7706dc346a647ecd99211
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a>Prise en charge de Skype Entreprise Online avec Outlook sur le Web

Outlook sur le web (Outlook Web App) dans Office 365 propose une base Skype pour client web Business à partir de la barre de navigation. Ce client de base est disponible pour les utilisateurs en ligne dont admin n’a pas configuré une URL vanity pour leur organisation d’Office 365. Tant que le compte d’utilisateur est en ligne et n’a pas une URL de courtoisie, ils pourront toujours voir l’expérience même si leur organisation a certains comptes d’utilisateurs qui sont hébergées sur site. Les utilisateurs qui ont des utilisateurs comptes locaux (qu’ils aient une URL vanity ou non) ou sont gérés par Microsoft verront l’expérience Lync dans Outlook web app.
  
Le tableau suivant récapitule les différentes configurations dont vous disposez et le client web qui est utilisé.
  
||||
|:-----|:-----|:-----|
|**Le compte utilisateur est** <br/> |**Une URL de redirection vers un microsite est configurée ou il existe une configuration dédiée** <br/> |**Expérience Skype Entreprise ou Lync ?** <br/> |
|Online  <br/> |Non  <br/> |Expérience Web Skype Entreprise  <br/> |
|Online  <br/> |Oui  <br/> |Expérience Web Lync  <br/> |
|Hybride mais domicilié en ligne  <br/> |Non  <br/> |Expérience Web Skype Entreprise  <br/> |
|Hybride mais domicilié en ligne  <br/> |Oui  <br/> |Expérience Web Lync  <br/> |
|Hybride mais domicilié sur site  <br/> |Non  <br/> |Expérience Web Lync  <br/> |
|Hybride mais domicilié sur site  <br/> |Oui  <br/> |Expérience Web Lync  <br/> |
|Pur sur prem  <br/> |Non  <br/> |Expérience Web Lync  <br/> |
|Pur sur prem  <br/> |Oui  <br/> |Expérience Web Lync  <br/> |
   

## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)

[Permettent d’ajouter des contacts de Skype Skype pour les utilisateurs professionnels](let-skype-for-business-users-add-skype-contacts.md)