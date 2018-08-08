---
title: Configuration requise des clients Windows et prise en charge logicielle
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Résumé : Passez en revue les exigences de prise en charge du client Windows lors de la planification Skype pour Business Server.'
ms.openlocfilehash: 161933f5982919376dd6c9610d47c78866316cdc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20984952"
---
# <a name="windows-client-requirements-and-software-support"></a>Configuration requise des clients Windows et prise en charge logicielle
 
**Résumé :** Passez en revue les exigences de prise en charge du client Windows lors de la planification Skype pour Business Server.
  
Cette section récapitule les logiciels requis pour prendre en charge la Skype pour les clients Windows de l’entreprise.  Ces clients sont installés lors de l’installation d’Office 365 et sont également disponibles au [Téléchargement de Skype pour les entreprises sur tous les périphériques de votre](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> Le complément de réunion en ligne pour Skype pour les entreprises, qui prend en charge la gestion des réunions dans le client de messagerie et de collaboration Outlook, s’installe automatiquement avec Skype pour les entreprises. 
  
**Logiciels requis pour Skype pour client d’entreprise et le complément de réunion en ligne**

|**Composant système**|**Versions prises en charge**|
|:-----|:-----|
|Système d’exploitation Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> système d’exploitation Windows 7  <br/> Windows Server 2008 R2 ou versions ultérieures avec le service pack le plus récent  <br/> **Remarque :** Skype pour les entreprises et le complément de réunion en ligne pour Skype pour les entreprises ne sont pas pris en charge sur Windows Vista ou Windows XP (n’importe quelle version). <br/> |
|Installation et mises à jour  <br/> |Droits et autorisations d’administrateur  <br/> |
|Navigateur  <br/> |Microsoft Edge  <br/> Navigateur Internet d’Internet Explorer 11  <br/>  Navigateur Internet d’Internet Explorer 10 <br/> Navigateur Internet d’Internet Explorer 9  <br/> Navigateur Internet d’Internet Explorer 8  <br/> Navigateur Internet d’Internet Explorer 7  <br/> Navigateur web Mozilla Firefox  <br/>  Navigateur Google Chrome  <br/>**Remarque :** Si vous utilisez Skype pour les entreprises avec Microsoft Exchange Online et votre organisation a déployé un proxy HTTP d’authentification, Internet Explorer 8 ou version ultérieure est requis.           |
|Intégration à Microsoft Office  <br/> | Outlook 2010 ou version ultérieure |
|Intégration à Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 ou version ultérieure  | 
   
## <a name="hardware"></a>Configuration matérielle

Reportez-vous à la [Configuration requise pour](https://products.office.com/en-us/office-system-requirements) Office 365 pour le matériel requis pour exécuter le Skype pour le client Business.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Application de réunions Skype et Skype pour Business Web App 

L’application des réunions Skype et Skype pour l’application Web de gestion des prend en charge les combinaisons de systèmes d’exploitation et de navigateurs. Pour plus d’informations, voir [Plan pour les clients de réunions (application Web et application de réunions)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Utilisation de profils obligatoires

Si vous prévoyez d’utiliser le Skype pour les fonctionnalités de conférence, évitez d’utiliser des profils obligatoires des Services de domaine Active Directory pour vous connecter à la Skype pour client d’entreprise. Étant donné que les profils obligatoires sont des profils utilisateur en lecture seule, les clés de l’infrastructure à clé publique (PKI) qui sont requis pour Skype pour la conférence Business ne peut pas être enregistrés dans le profil. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Configuration requise pour Skype Entreprise pour Windows Phone
 
 
Microsoft Skype pour Business pour Windows Phone fournit la messagerie instantanée, présence enrichie et téléphonie aux utilisateurs de votre organisation qui sont connectent à partir d’un smartphone ou un appareil mobile Windows Professionnel. Les appareils mobiles permettent aux utilisateurs d’étendre la portée de Skype pour les entreprises. Cette rubrique décrit les considérations de planification pour Skype pour Business pour Windows Phone qui incluent l’identification des conditions préalables et les exigences techniques, les composants requis et déploiement.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Configuration requise pour Skype Entreprise pour Windows Phone

Vous trouverez ci-dessous la Skype pour les composants requis Business pour Windows Phone.
  
- Windows Phone 8.1 ou version ultérieure.
    
- Les dernières mises à jour Microsoft doivent être installées sur l’appareil Windows Phone. Pour plus d’informations, consultez la section Windows Phone 8.1 à [Windows Phone 8 mise à jour de l’historique](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- L’appareil doit disposer d’au moins 22 Mo d’espace disque disponible.
    
- L’utilisateur doit avoir souscrit un plan de données et de communications vocales auprès d’un fournisseur.


## <a name="see-also"></a>Voir aussi

[Planifier pour les clients de réunions (application Web et application de réunions)](meetings-clients.md)
  
[Skype pour les entreprises sur la configuration requise des clients Mac](mac-requirements.md)

[Télécharger Skype pour les entreprises sur tous les périphériques de votre](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Requise pour Office 365](https://products.office.com/en-us/office-system-requirements)