---
title: Windows client et prise en charge des logiciels
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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Résumé : Examinez les exigences Windows prise en charge du client lors de la planification Skype Entreprise Server.'
ms.openlocfilehash: 755f60030c905bfb5a5f488e2573c12b3396ab1e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627946"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows client et prise en charge des logiciels
 
**Résumé :** Examinez les exigences Windows prise en charge du client lors de la planification Skype Entreprise Server.
  
Cette section récapitule les logiciels requis pour prendre en charge Skype Entreprise Windows clients. Ces clients sont installés lors Microsoft 365 ou Office 365' installation, et sont également disponibles à la Skype Entreprise sur tous [vos appareils.](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
> [!NOTE]
> Le add-in de réunion en ligne pour Skype Entreprise, qui prend en charge la gestion des réunions à partir du client de messagerie et de collaboration Outlook, s’installe automatiquement avec Skype Entreprise. 
  
**Logiciel requis pour Skype Entreprise client et le module de réunion en ligne**

|**Composant système**|**Versions prises en charge**|
|:-----|:-----|
|Windows Système d'exploitation  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 ou version ultérieure avec le dernier Service Pack  <br/> **Remarque :** Skype Entreprise et le Skype Entreprise de réunion en ligne ne sont pas pris en charge sur Windows Vista ou Windows XP (n’importe quelle version). <br/> |
|Installation et mises à jour  <br/> |Droits et autorisations d’administrateur  <br/> |
|Navigateur  <br/> |Microsoft Edge  <br/> Navigateur Internet Explorer 11  <br/>  Internet Explorer 10 navigateur Internet <br/> Navigateur Internet Internet d’Internet Explorer 9  <br/> Navigateur Internet Explorer 8  <br/> Navigateur Internet Internet d’Internet Explorer 7  <br/> Navigateur web Mozilla Firefox  <br/>  Navigateur web Google Chrome  <br/>**Remarque :** Si vous utilisez Skype Entreprise avec Microsoft Exchange Online et que votre organisation a déployé un proxy HTTP d’authentification, Internet Explorer 8 ou une ultérieure est requis.           |
|Intégration à Microsoft Office  <br/> | Outlook 2010 ou version ultérieure |
|Intégration à Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 ou ultérieure  | 
   
## <a name="hardware"></a>Matériel

Reportez-vous aux Microsoft 365 et Office [système](https://products.office.com/office-system-requirements) requis pour le matériel requis pour exécuter le client Skype Entreprise client.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype Application et Application Web Skype Entreprise meetings 

L’application Skype Meetings et Application Web Skype Entreprise des combinaisons spécifiques de systèmes d’exploitation et de navigateurs. Pour plus d’informations, voir [Plan for Meetings clients (Web App and Meetings App).](meetings-clients.md) 
  
## <a name="using-mandatory-profiles"></a>Utilisation de profils obligatoires

Si vous prévoyez d’utiliser les fonctionnalités de conférence Skype Entreprise, évitez d’utiliser les profils obligatoires des services de domaine Active Directory pour vous Skype Entreprise client. Étant donné que les profils obligatoires sont des profils utilisateur en lecture seule, les clés d’infrastructure à clé publique (PKI) requises pour la conférence Skype Entreprise ne peuvent pas être enregistrées dans le profil. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>System requirements for Skype Entreprise pour Windows Phone
 
 
Microsoft Skype Entreprise pour Windows Phone fournit des fonctionnalités de messagerie instantanée, de présence améliorée et de téléphonie pour les utilisateurs de votre organisation qui se connectent à partir d’un smartphone ou d’un Windows Professional mobile. Les appareils mobiles permettent aux utilisateurs d’étendre la portée Skype Entreprise. Cette rubrique décrit les considérations relatives à la planification des Skype Entreprise pour Windows Phone notamment l’identification des conditions préalables et techniques requises, les composants requis et les instructions de déploiement.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Skype Entreprise pour Windows Phone Conditions préalables

Les conditions préalables Skype Entreprise pour Windows Phone suivantes sont les suivantes.
  
- Windows Phone 8.1 ou ultérieure.
    
- Le Windows Phone doit avoir les dernières mises à jour disponibles auprès de Microsoft. Pour plus d’informations, consultez la section Windows Phone 8.1 sur [Windows Phone 8 historique des](https://go.microsoft.com/fwlink/p/?LinkID=281961)mises à jour.
    
- L’appareil doit avoir 22 Mo d’espace disque disponible.
    
- L’utilisateur doit avoir souscrit un plan de données et de communications vocales auprès d’un fournisseur.


## <a name="see-also"></a>Voir aussi

[Planifier les clients Meetings (application Web et application réunions)](meetings-clients.md)
  
[Skype Entreprise client sur Mac](mac-requirements.md)

[Télécharger Skype Entreprise sur tous vos appareils](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Microsoft 365 et Office système requis](https://products.office.com/office-system-requirements)
