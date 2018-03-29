---
title: Déploiement des clients pour Skype Entreprise Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Résumé : Vue d’ensemble des méthodes d’installation de client entreprise pour Skype pour les entreprises.'
ms.openlocfilehash: d41ce5b2fe9b4717a9af78fb3072ae0da48b72ec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-clients-for-skype-for-business-server-2015"></a>Déploiement des clients pour Skype Entreprise Server 2015
 
**Résumé :** Vue d’ensemble des méthodes d’installation de client entreprise pour Skype pour les entreprises.
  
Comment déployer Skype pour entreprise à vos utilisateurs dépend de si vous avez acheté Skype pour les entreprises dans le cadre d’un plan d’Office 365, ou vous avez acheté une version sous licence de volume de Skype pour les entreprises. 
  
- **Office 365** Si vous avez un plan Office 365 incluant Skype pour les entreprises, la technologie d’installation qui est utilisée est appelée Click-to-Run. Avec Office 365, vous pouvez permettre à vos utilisateurs installer Skype pour entreprise pour eux-mêmes à partir du portail Office 365. Ou bien, vous pouvez déployer Skype pour entreprise à vos utilisateurs en téléchargement du logiciel sur votre réseau local, puis à l’aide de vos outils de déploiement de logiciel existant, par exemple avec Microsoft System Center Configuration Manager. Pour plus d’informations d’installation sur Skype pour entreprise qui est fourni avec Office 365, voir [déployer le Skype pour client d’entreprise dans Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Licences en volume** Si vous avez une version de licence en volume de Skype pour les entreprises, la technologie d’installation qui est utilisée est Windows Installer (MSI). Un package d’installation Windows Installer se compose de plusieurs fichiers MSI. Pour qu’un package MSI principal indépendant de la langue soit complet, il est accompagné d’un ou de plusieurs packages spécifiques à la langue. Le programme d’installation assemble les packages individuels et effectue des tâches de personnalisation et de maintenance pendant et après l’installation d’Office sur les ordinateurs des utilisateurs.
    
Les rubriques de cette section décrivent comment utiliser et personnaliser le programme d’installation de Windows pour déployer le Skype pour client d’entreprise à vos utilisateurs par le biais de vos procédures habituelles.
  
> [!NOTE]
> En ligne complément de réunion pour Skype pour les entreprises, qui prend en charge la réunion de gestion depuis Outlook client de messagerie et de collaboration, installe automatiquement avec Skype pour les entreprises. 
  
> [!NOTE]
> Le programme d’installation de Office 365 ne désinstalle pas les versions précédentes de Lync ou Communicator d’Office. Le Skype pour client d’entreprise installe côte à côte avec d’autres clients Lync ou Communicator d’Office. 
  
## <a name="installing-windows-clients"></a>L’installation des clients Windows

- [Personnaliser l’installation du client Windows dans Skype pour Business Server 2015](customize-windows-client-installation.md)
    
- [Configurer l’expérience client avec Skype pour entreprise](configure-the-client-experience.md)
    
- [Configurer la liste de contacts Smart dans Skype pour Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Installation de périphériques clients

- [Installation et test Skype pour Business pour Windows Phone](windows-phone.md)
    
- [Installation et test Skype pour entreprise pour iOS](ios.md)
    
- [Déployer un système de salle de Skype dans Skype pour Business Server](deploy-skype-room-system.md)
    
- [Déployer Skype salle systèmes v2](room-systems-v2.md)
    
- [Déploiement de la VDI Lync plug-in avec Skype Business Server 2015](deploy-the-lync-vdi-plug-in.md)
    
- [Déployer des clients Web téléchargeables Skype pour Business Server 2015](deploy-web-downloadable-clients.md)
    
- [Personnaliser l’expérience de client Mac dans Skype pour entreprise](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Voir aussi

#### 

[Déployer le Skype pour client d’entreprise pour votre organisation](https://support.officeppe.com/en-us/article/Deploy-the-Skype-for-Business-client-for-your-organization-8c563b81-22c9-4024-9efe-9fe28c7bbc96?ui=en-US&amp;rs=en-US&amp;ad=US)

