---
title: Prise en charge de Skype Entreprise Online avec Outlook sur le Web
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Outlook sur le Web (Outlook Web App) dans Office 365 offre un client Web Skype Entreprise standard depuis la barre de navigation. Ce client de base est disponible pour les utilisateurs en ligne dont admin n’a pas encore configuré une URL de redirection pour leur organisation Office 365. Tant que le compte d’utilisateur est en ligne et ne possède pas une URL de redirection, ils verront toujours l’expérience même si leur organisation a certains comptes d’utilisateurs qui sont hébergés sur un système local. Les utilisateurs qui possèdent des utilisateur comptes locaux (si elles ont une URL de redirection ou non) ou qui sont gérés par Microsoft verront l’expérience de Lync dans Outlook web app.
ms.openlocfilehash: 112da508d0f21175d309679a529f86d22a37d0d4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23863244"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a>Prise en charge de Skype Entreprise Online avec Outlook sur le Web

Outlook sur le Web (Outlook Web App) dans Office 365 offre un client Web Skype Entreprise standard depuis la barre de navigation. Ce client de base est disponible pour les utilisateurs en ligne dont admin n’a pas encore configuré une URL de redirection pour leur organisation Office 365. Tant que le compte d’utilisateur est en ligne et ne possède pas une URL de redirection, ils verront toujours l’expérience même si leur organisation a certains comptes d’utilisateurs qui sont hébergés sur un système local. Les utilisateurs qui possèdent des utilisateur comptes locaux (si elles ont une URL de redirection ou non) ou qui sont gérés par Microsoft verront l’expérience de Lync dans Outlook web app.
  
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

[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 