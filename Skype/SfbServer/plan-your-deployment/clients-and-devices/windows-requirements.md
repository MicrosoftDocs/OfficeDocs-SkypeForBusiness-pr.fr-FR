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
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Résumé: Examinez la configuration requise du support client Windows lors de la planification de Skype entreprise Server.'
ms.openlocfilehash: bbcbf11da53b2895f04725fda57342c17989b7f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277271"
---
# <a name="windows-client-requirements-and-software-support"></a>Configuration requise pour le client Windows et prise en charge logicielle
 
**Résumé:** Passez en revue la configuration requise pour le client Windows lors de la planification de Skype entreprise Server.
  
Cette section résume les logiciels nécessaires à la prise en charge des clients Windows Skype entreprise.  Ces clients sont installés lors de l’installation d’Office 365 et sont également disponibles sur [le site Télécharger Skype entreprise sur tous vos appareils](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> Le complément réunion en ligne pour Skype entreprise, qui prend en charge la gestion de la réunion à partir du client de messagerie et de collaboration Outlook, s’installe automatiquement avec Skype entreprise. 
  
**Logiciel requis pour le client Skype entreprise et le complément réunion en ligne**

|**Composant système**|**Versions prises en charge**|
|:-----|:-----|
|Système d’exploitation Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Système d’exploitation Windows 7  <br/> Windows Server 2008 R2 ou version ultérieure avec le dernier Service Pack  <br/> **Remarque:** Skype entreprise et le complément réunion en ligne pour Skype entreprise ne sont pas pris en charge sur Windows Vista ou Windows XP (n’importe quelle version). <br/> |
|Installation et mises à jour  <br/> |Droits et autorisations d’administrateur  <br/> |
|Navigateur  <br/> |Microsoft Edge  <br/> Navigateur Internet Explorer 11  <br/>  Navigateur Internet d’Internet Explorer 10 <br/> Navigateur Internet Explorer 9  <br/> Navigateur Internet Explorer 8  <br/> Navigateur Internet Explorer 7  <br/> Navigateur web Mozilla Firefox  <br/>  Navigateur Web Google Chrome  <br/>**Remarque:** Si vous utilisez Skype entreprise avec Microsoft Exchange Online et que votre organisation a déployé un proxy HTTP d’authentification, Internet Explorer 8 ou version ultérieure est requis.           |
|Intégration à Microsoft Office  <br/> | Outlook 2010 ou version ultérieure |
|Intégration à Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 ou version ultérieure  | 
   
## <a name="hardware"></a>Matériel

Pour connaître le matériel requis pour l’exécution du client Skype entreprise, consultez la [Configuration système requise](https://products.office.com/en-us/office-system-requirements) pour Office 365.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Application réunions Skype et Skype entreprise Web App 

L’application réunions Skype et Skype entreprise Web App prennent en charge des combinaisons spécifiques de systèmes d’exploitation et de navigateurs. Pour plus d’informations, reportez-vous à la rubrique [planification des clients de réunion (application Web et application réunions)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Utilisation de profils obligatoires

Si vous envisagez d’utiliser les fonctionnalités de conférence Skype entreprise, évitez d’utiliser les profils obligatoires de services de domaine Active Directory pour vous connecter au client Skype entreprise. Étant donné que les profils obligatoires sont des profils utilisateur en lecture seule, les clés d’infrastructure à clé publique (PKI) requises pour les conférences Skype entreprise ne peuvent pas être enregistrées dans le profil. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Configuration requise pour Skype Entreprise pour Windows Phone
 
 
Microsoft Skype entreprise pour Windows Phone fournit des fonctionnalités de messagerie instantanée, de présence améliorée et de téléphonie pour les utilisateurs de votre organisation qui se connectent à partir d’un smartphone ou d’un appareil mobile Windows professionnel. Les appareils mobiles permettent aux utilisateurs de prolonger la portée de Skype entreprise. Cette rubrique décrit les considérations en matière de planification pour Skype entreprise pour Windows Phone qui incluent l’identification des éléments requis et des exigences techniques, des composants requis et des instructions de déploiement.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Configuration requise pour Skype Entreprise pour Windows Phone

Vous trouverez ci-après les conditions préalables pour Skype entreprise pour Windows Phone.
  
- Windows Phone 8.1 ou version ultérieure.
    
- Les dernières mises à jour Microsoft doivent être installées sur l’appareil Windows Phone. Pour plus d’informations, reportez-vous à la section Windows Phone 8,1 dans l' [historique des mises à jour Windows Phone 8](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- L’appareil doit disposer d’au moins 22 Mo d’espace disque disponible.
    
- L’utilisateur doit avoir souscrit un plan de données et de communications vocales auprès d’un fournisseur.


## <a name="see-also"></a>Voir aussi

[Planifier pour les clients de conférences (application Web et application réunions)](meetings-clients.md)
  
[Configuration requise pour le client Skype entreprise pour Mac](mac-requirements.md)

[Télécharger Skype entreprise sur tous vos appareils](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Configuration système requise pour Office 365](https://products.office.com/en-us/office-system-requirements)
