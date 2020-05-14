---
title: Configuration requise pour le client Windows et prise en charge logicielle
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Résumé : passez en revue les exigences de prise en charge du client Windows lors de la planification de Skype entreprise Server.'
ms.openlocfilehash: 67208fc25344ff417094419f22068822e03b13db
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219824"
---
# <a name="windows-client-requirements-and-software-support"></a>Configuration requise pour le client Windows et prise en charge logicielle
 
**Résumé :** Passez en revue les exigences de prise en charge du client Windows lors de la planification de Skype entreprise Server.
  
Cette section récapitule les logiciels requis pour prendre en charge les clients Windows Skype entreprise. Ces clients sont installés lors de l’installation de Microsoft 365 ou Office 365, et sont également disponibles à [l’adresse Télécharger Skype entreprise sur tous vos appareils](https://products.office.com/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> Le complément de réunion en ligne pour Skype entreprise, qui prend en charge la gestion des réunions à partir du client de messagerie et de collaboration Outlook, s’installe automatiquement avec Skype entreprise. 
  
**Logiciels requis pour le client Skype entreprise et le complément de réunion en ligne**

|**Composant système**|**Versions prises en charge**|
|:-----|:-----|
|Système d’exploitation Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 ou version ultérieure avec le Service Pack le plus récent  <br/> **Remarque :** Skype entreprise et le complément de réunion en ligne pour Skype entreprise ne sont pas pris en charge sur Windows Vista ou Windows XP (toutes les versions). <br/> |
|Installation et mises à jour  <br/> |Droits et autorisations d’administrateur  <br/> |
|Navigateur  <br/> |Microsoft Edge  <br/> Internet Explorer 11 navigateur Internet  <br/>  Internet Explorer 10 navigateur Internet <br/> Navigateur Internet Explorer 9  <br/> Navigateur Internet Explorer 8  <br/> Navigateur Internet Explorer 7  <br/> Navigateur web Mozilla Firefox  <br/>  Navigateur Web Google Chrome  <br/>**Remarque :** Si vous utilisez Skype entreprise avec Microsoft Exchange Online et que votre organisation a déployé un proxy HTTP d’authentification, Internet Explorer 8 ou une version ultérieure est requis.           |
|Intégration à Microsoft Office  <br/> | Outlook 2010 ou version ultérieure |
|Intégration à Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 ou version ultérieure  | 
   
## <a name="hardware"></a>Matériel

Reportez-vous à la [Configuration requise](https://products.office.com/office-system-requirements) de Microsoft 365 et Office System pour le matériel requis pour exécuter le client Skype entreprise.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Application de réunions Skype et Skype entreprise Web App 

L’application réunions Skype et Skype entreprise Web App prennent en charge des combinaisons spécifiques de systèmes d’exploitation et de navigateurs. Pour plus d’informations, reportez-vous à la rubrique [plan for meetings clients (Web App and Meetings App)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Utilisation de profils obligatoires

Si vous envisagez d’utiliser les fonctionnalités de conférence Skype entreprise, évitez d’utiliser les profils obligatoires des services de domaine Active Directory pour se connecter au client Skype entreprise. Étant donné que les profils obligatoires sont des profils utilisateur en lecture seule, les clés d’infrastructure à clé publique (PKI) requises pour les conférences Skype entreprise ne peuvent pas être enregistrées dans le profil. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Configuration système requise pour Skype entreprise pour Windows Phone
 
 
Microsoft Skype entreprise pour Windows Phone offre des fonctionnalités de messagerie instantanée, de présence améliorée et de téléphonie pour les utilisateurs de votre organisation qui se connectent à partir d’un smartphone ou d’un appareil mobile Windows professionnel. Les appareils mobiles permettent aux utilisateurs d’étendre la portée de Skype entreprise. Cette rubrique décrit les considérations relatives à la planification de Skype entreprise pour Windows Phone qui incluent l’identification des conditions préalables et des exigences techniques, les composants requis et les instructions de déploiement.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Configuration requise pour Skype entreprise pour Windows Phone

Voici les conditions préalables de Skype entreprise pour Windows Phone.
  
- Windows Phone 8,1 ou version ultérieure.
    
- L’appareil Windows Phone doit disposer des dernières mises à jour disponibles auprès de Microsoft. Pour plus d’informations, reportez-vous à la section Windows Phone 8,1 à l' [historique des mises à jour Windows Phone 8](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- L’appareil doit disposer de 22 Mo d’espace disque disponible.
    
- L’utilisateur doit avoir souscrit un plan de données et de communications vocales auprès d’un fournisseur.


## <a name="see-also"></a>Voir aussi

[Planifier les clients des réunions (application Web et application de réunion)](meetings-clients.md)
  
[Configuration requise pour les clients Skype entreprise sur Mac](mac-requirements.md)

[Télécharger Skype entreprise sur tous vos appareils](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Configuration requise pour Microsoft 365 et Office System](https://products.office.com/office-system-requirements)
