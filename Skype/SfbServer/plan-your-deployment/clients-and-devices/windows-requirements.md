---
title: Exigences du client Windows et prise en charge des logiciels
ms.author: v-cichur
author: cichur
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
description: 'Résumé : Examinez les exigences de prise en charge du client Windows lors de la planification de Skype Entreprise Server.'
ms.openlocfilehash: 105c4ec8824b2b6f5f7a68349659ca10bb82c737
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816064"
---
# <a name="windows-client-requirements-and-software-support"></a>Exigences du client Windows et prise en charge des logiciels
 
**Résumé :** Examinez les exigences de prise en charge du client Windows lors de la planification de Skype Entreprise Server.
  
Cette section récapitule les logiciels requis pour prendre en charge les clients Windows Skype Entreprise. Ces clients sont installés lors de l’installation de Microsoft 365 ou Office 365, et sont également disponibles sur télécharger Skype Entreprise sur tous [vos appareils.](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
> [!NOTE]
> Le module de réunion en ligne pour Skype Entreprise, qui prend en charge la gestion des réunions à partir du client de messagerie et de collaboration Outlook, s’installe automatiquement avec Skype Entreprise. 
  
**Logiciel requis pour le client Skype Entreprise et le module de réunion en ligne**

|**Composant système**|**Versions prises en charge**|
|:-----|:-----|
|Système d’exploitation Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 ou version ultérieure avec le Service Pack le plus récent  <br/> **Remarque :** Skype Entreprise et le module de réunion en ligne pour Skype Entreprise ne sont pas pris en charge sur Windows Vista ou Windows XP (n’importe quelle version). <br/> |
|Installation et mises à jour  <br/> |Droits et autorisations d’administrateur  <br/> |
|Navigateur  <br/> |Microsoft Edge  <br/> Navigateur Internet Explorer 11  <br/>  Navigateur Internet Explorer 10 <br/> Navigateur Internet Explorer 9  <br/> Navigateur Internet Explorer 8  <br/> Navigateur Internet Explorer 7  <br/> Navigateur web Mozilla Firefox  <br/>  Navigateur web Google Chrome  <br/>**Remarque :** Si vous utilisez Skype Entreprise avec Microsoft Exchange Online et que votre organisation a déployé un proxy HTTP d’authentification, Internet Explorer 8 ou une ultérieure est requis.           |
|Intégration à Microsoft Office  <br/> | Outlook 2010 ou version ultérieure |
|Intégration à Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 ou ultérieure  | 
   
## <a name="hardware"></a>Matériel

Reportez-vous à la configuration requise pour Microsoft 365 et Office [System](https://products.office.com/office-system-requirements) pour le matériel requis pour exécuter le client Skype Entreprise.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Application Réunions Skype et Skype Entreprise Web App 

L’application réunions Skype et Skype Entreprise Web App prise en charge des combinaisons spécifiques de systèmes d’exploitation et de navigateurs. Pour plus d’informations, voir [Plan for Meetings clients (Web App and Meetings App).](meetings-clients.md) 
  
## <a name="using-mandatory-profiles"></a>Utilisation de profils obligatoires

Si vous envisagez d’utiliser les fonctionnalités de conférence Skype Entreprise, évitez d’utiliser les profils obligatoires des services de domaine Active Directory pour vous inscrire au client Skype Entreprise. Étant donné que les profils obligatoires sont des profils utilisateur en lecture seule, les clés d’infrastructure à clé publique (PKI) requises pour la conférence Skype Entreprise ne peuvent pas être enregistrées dans le profil. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>System requirements for Skype for Business for Windows Phone
 
 
Microsoft Skype Entreprise pour Windows Phone fournit des fonctionnalités de messagerie instantanée, de présence améliorée et de téléphonie pour les utilisateurs de votre organisation qui se connectent à partir d’un smartphone ou d’un appareil mobile Windows Professionnel. Les appareils mobiles permettent aux utilisateurs d’étendre la portée de Skype Entreprise. Cette rubrique décrit les considérations relatives à la planification de Skype Entreprise pour Windows Phone, notamment l’identification des conditions préalables et des exigences techniques, les composants requis et les instructions de déploiement.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Conditions préalables pour Skype Entreprise pour Windows Phone

Voici les conditions préalables de Skype Entreprise pour Windows Phone.
  
- Windows Phone 8.1 ou ultérieur.
    
- Les dernières mises à jour de Microsoft doivent être disponibles sur l’appareil Windows Phone. Pour plus d’informations, consultez la section Windows Phone 8.1 de l’historique des mises à jour [de Windows Phone 8.](https://go.microsoft.com/fwlink/p/?LinkID=281961)
    
- L’appareil doit avoir 22 Mo d’espace disque disponible.
    
- L’utilisateur doit avoir souscrit un plan de données et de communications vocales auprès d’un fournisseur.


## <a name="see-also"></a>Voir aussi

[Planifier les clients Meetings (application Web et application réunions)](meetings-clients.md)
  
[Skype Entreprise sur Mac : exigences en matière de client](mac-requirements.md)

[Télécharger Skype Entreprise sur tous vos appareils](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Microsoft 365 et office system requirements](https://products.office.com/office-system-requirements)
