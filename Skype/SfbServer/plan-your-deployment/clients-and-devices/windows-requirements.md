---
title: Configuration requise du client Windows et prise en charge des logiciels
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Résumé : Passez en revue les exigences de prise en charge de client de Windows lors de la planification de Skype pour Business Server 2015.'
ms.openlocfilehash: 1a9af80b55073240a53843c9fee912c0c521ba73
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="windows-client-requirements-and-software-support"></a>Configuration requise du client Windows et prise en charge des logiciels
 
**Résumé :** Passez en revue les exigences de prise en charge de client de Windows lors de la planification de Skype pour Business Server 2015.
  
Cette section récapitule les logiciels requis pour prendre en charge le Skype pour entreprise 2015 2016 clients et Windows.
  
Ces clients sont installés lors de l’installation d’Office 365 et sont également disponibles au [Téléchargement de Skype pour entreprise sur tous les périphériques](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> Le complément de réunion en ligne pour Skype pour les entreprises, qui prend en charge la gestion de réunion depuis le client de messagerie et de collaboration Outlook, s’installe automatiquement avec Skype pour les entreprises. 
  
**Logiciels requis pour Skype pour les entreprises et la réunion en ligne complément pour Skype pour entreprise**


|**Composant du système**|**Versions prises en charge**|
|:-----|:-----|
|Système d’exploitation Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> système d’exploitation Windows 7  <br/> Windows Server 2008 R2 avec le dernier service pack  <br/> **Remarque :** Skype pour les entreprises et le complément de réunion en ligne pour Skype pour les entreprises ne sont pas pris en charge sur Windows Vista ou Windows XP (toutes les versions). <br/> |
|Installation et mises à jour  <br/> |Droits et autorisations d’administrateur  <br/> |
|Navigateur  <br/> |Microsoft Edge  <br/> Navigateur Internet de Internet Explorer 11  <br/>  Navigateur Internet de Internet Explorer 10 <br/> Navigateur Internet de Internet Explorer 9  <br/> Navigateur Internet de Internet Explorer 8  <br/> Navigateur Internet de Internet Explorer 7  <br/> Navigateur web Mozilla Firefox  <br/> **Remarque :** Si vous utilisez Skype pour entreprise avec Microsoft Exchange Online et votre organisation a déployé un proxy HTTP d’authentification, Internet Explorer 8 ou une version ultérieure est requis.           |
|Intégration à Microsoft Office  <br/> |Pour le jeu complet de fonctionnalités d’intégration :  <br/> Client de messagerie et de collaboration • outlook 2016  <br/> Client de messagerie et de collaboration • outlook 2013  <br/> Client de messagerie et de collaboration • outlook 2010  <br/> |
|Intégration à Microsoft Exchange  <br/> |• Microsoft Exchange Server 2016  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2010  <br/> |
   
## <a name="hardware"></a>Matériel

Reportez-vous à Office 365 [requise](https://products.office.com/en-us/office-system-requirements) pour le matériel nécessaire pour exécuter le Skype pour client d’entreprise.
  
## <a name="skype-for-business-web-app-browsers"></a>Skype pour les navigateurs de Business Web App

Skype pour Business Web App prend en charge les combinaisons de systèmes d’exploitation et des navigateurs spécifiques. Pour plus d’informations, consultez [planification pour les clients de réunions (application Web et application de réunions)](meetings-clients.md). 
  
## <a name="microsoft-office-supportability"></a>Capacité de prise en charge de Microsoft Office

Skype pour les clients d’entreprise serveur 2015 prend en charge l’intégration avec les différentes versions de Microsoft Office.
  
- Skype pour les fonctionnalités d’intégration métier sont pris en charge dans Outlook 2010, Outlook 2013 et 2016 d’Outlook.
    
- Skype pour les fonctionnalités d’intégration métier sont pris en charge sur Microsoft Exchange Server 2010 2016 de Microsoft Exchange Server et Microsoft Exchange Server 2013.
    
- Le complément de réunion en ligne pour Skype pour entreprise est pris en charge avec Microsoft Office 2010, Office 2013 et 2016 d’Office.
    
## <a name="using-mandatory-profiles"></a>Utilisation de profils obligatoires

Si vous envisagez d’utiliser le Skype pour les fonctionnalités de conférence Business, évitez d’utiliser des profils obligatoires des Services de domaine Active Directory pour vous connecter à la Skype pour client d’entreprise. Parce que les profils obligatoires sont des profils utilisateur en lecture seule, les clés de l’infrastructure à clé publique (PKI) qui sont requis pour Skype pour la conférence de l’entreprise ne peut pas enregistrés dans le profil. 
  
## <a name="macintosh-operating-systems"></a>Systèmes d’exploitation Macintosh

Le Skype pour le commerce sur les exigences en matière de prise en charge de Mac sont détaillés dans [Skype pour le commerce sur la configuration du client Mac](mac-requirements.md).
  
## <a name="see-also"></a>Voir aussi

#### 

[Planifier des clients de réunions (Web App et réunions App)](meetings-clients.md)
  
[Skype pour le commerce sur la configuration du client Mac](mac-requirements.md)
#### 

[Télécharger Skype pour entreprise sur tous les périphériques de votre](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Requise pour Office 365](https://products.office.com/en-us/office-system-requirements)

