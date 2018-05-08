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
description: 'Résumé : Passez en revue les exigences de prise en charge du client Windows lors de la planification Skype pour Business Server 2015.'
ms.openlocfilehash: 3dac3a8e15e53cec5605aa2b003150f491d8f2b5
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="windows-client-requirements-and-software-support"></a>Configuration requise des clients Windows et prise en charge logicielle
 
**Résumé :** Passez en revue les exigences de prise en charge du client Windows lors de la planification Skype pour Business Server 2015.
  
Cette section récapitule les logiciels requis pour prendre en charge la Skype pour Business 2015 2016 clients et Windows.
  
Ces clients sont installés lors de l’installation d’Office 365 et sont également disponibles au [Téléchargement de Skype pour les entreprises sur tous les périphériques de votre](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> Le complément de réunion en ligne pour Skype pour les entreprises, qui prend en charge la gestion des réunions dans le client de messagerie et de collaboration Outlook, s’installe automatiquement avec Skype pour les entreprises. 
  
**Logiciels requis pour Skype pour les entreprises et la réunion en ligne complément pour Skype pour les entreprises**


|**Composant système**|**Versions prises en charge**|
|:-----|:-----|
|Système d’exploitation Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> système d’exploitation Windows 7  <br/> Windows Server 2008 R2 avec le service pack le plus récent  <br/> **Remarque :** Skype pour les entreprises et le complément de réunion en ligne pour Skype pour les entreprises ne sont pas pris en charge sur Windows Vista ou Windows XP (n’importe quelle version). <br/> |
|Installation et mises à jour  <br/> |Droits et autorisations d’administrateur  <br/> |
|Navigateur  <br/> |Microsoft Edge  <br/> Navigateur Internet d’Internet Explorer 11  <br/>  Navigateur Internet d’Internet Explorer 10 <br/> Navigateur Internet d’Internet Explorer 9  <br/> Navigateur Internet d’Internet Explorer 8  <br/> Navigateur Internet d’Internet Explorer 7  <br/> Navigateur web Mozilla Firefox  <br/> **Remarque :** Si vous utilisez Skype pour les entreprises avec Microsoft Exchange Online et votre organisation a déployé un proxy HTTP d’authentification, Internet Explorer 8 ou version ultérieure est requis.           |
|Intégration à Microsoft Office  <br/> |Pour le jeu complet de fonctionnalités d’intégration :  <br/> • 2016 outlook de client de messagerie et de collaboration  <br/> Client de messagerie et de collaboration • outlook 2013  <br/> Client de messagerie et de collaboration • outlook 2010  <br/> |
|Intégration à Microsoft Exchange  <br/> |• Microsoft Exchange Server 2016  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2010  <br/> |
   
## <a name="hardware"></a>Configuration matérielle

Reportez-vous à la [Configuration requise pour](https://products.office.com/en-us/office-system-requirements) Office 365 pour le matériel requis pour exécuter le Skype pour le client Business.
  
## <a name="skype-for-business-web-app-browsers"></a>Skype correspondant aux navigateurs Web application métier

Skype pour Business Web App prend en charge les combinaisons de systèmes d’exploitation et de navigateurs. Pour plus d’informations, voir [Plan pour les clients de réunions (application Web et application de réunions)](meetings-clients.md). 
  
## <a name="microsoft-office-supportability"></a>Capacité de prise en charge de Microsoft Office

Skype pour les clients Business Server 2015 prend en charge l’intégration avec différentes versions de Microsoft Office.
  
- Skype pour les fonctionnalités d’intégration sont prises en charge 2016 Outlook, Outlook 2013 et Outlook 2010.
    
- Skype pour les fonctionnalités d’intégration sont pris en charge sur Microsoft Exchange Server 2016, Microsoft Exchange Server 2013 et Microsoft Exchange Server 2010.
    
- Le complément de réunion en ligne pour Skype pour les entreprises est pris en charge avec Office 2016, Office 2013 et Microsoft Office 2010.
    
## <a name="using-mandatory-profiles"></a>Utilisation de profils obligatoires

Si vous prévoyez d’utiliser le Skype pour les fonctionnalités de conférence, évitez d’utiliser des profils obligatoires des Services de domaine Active Directory pour vous connecter à la Skype pour client d’entreprise. Étant donné que les profils obligatoires sont des profils utilisateur en lecture seule, les clés de l’infrastructure à clé publique (PKI) qui sont requis pour Skype pour la conférence Business ne peut pas être enregistrés dans le profil. 
  
## <a name="macintosh-operating-systems"></a>Systèmes d’exploitation Macintosh

Le Skype pour les entreprises sur les exigences de prise en charge Mac sont détaillées dans [Skype pour les entreprises sur la configuration requise des clients Mac](mac-requirements.md).
  
## <a name="see-also"></a>Voir aussi

#### 

[Planifier pour les clients de réunions (application Web et application de réunions)](meetings-clients.md)
  
[Skype pour les entreprises sur la configuration requise des clients Mac](mac-requirements.md)
#### 

[Télécharger Skype pour les entreprises sur tous les périphériques de votre](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Requise pour Office 365](https://products.office.com/en-us/office-system-requirements)

