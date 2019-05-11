---
title: Déploiement de clients pour Skype pour Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Résumé : Vue d’ensemble des méthodes d’installation de client entreprise pour Skype pour les entreprises.'
ms.openlocfilehash: db5b1a4ed51aed5986cd954af9cdbecab208647d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893461"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Déploiement de clients pour Skype pour Business Server
 
**Résumé :** Vue d’ensemble des méthodes d’installation de client entreprise pour Skype pour les entreprises.
  
Comment déployer Skype pour les entreprises à vos utilisateurs dépend de si vous avez acheté Skype pour les entreprises dans le cadre d’un plan Office 365 ou que vous avez acheté une version sous licence en volume de Skype pour les entreprises. 
  
- **Office 365** Si vous disposez d’un plan Office 365 qui inclut Skype pour les entreprises, la technologie d’installation qui est utilisée est appelée Click-to-Run. Avec Office 365, vous pouvez permettre à vos utilisateurs installer Skype pour les entreprises pour eux-mêmes à partir du portail Office 365. Ou bien, vous pouvez déployer Skype pour les entreprises à vos utilisateurs à télécharger le logiciel sur votre réseau local, puis en utilisant vos outils de déploiement de logiciels existante, comme avec Microsoft System Center Configuration Manager. Pour plus d’informations d’installation sur Skype pour les entreprises qui est fourni avec Office 365, voir [déployer le Skype pour client d’entreprise dans Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Avec licence en volume** Si vous disposez d’une version sous licence en volume de la Skype pour Business 2015 ou client 2016, la technologie d’installation qui est utilisée est Windows Installer (MSI). Un package d’installation Windows Installer se compose de plusieurs fichiers .msi. Un package MSI indépendante de la langue principale est associé à un ou plusieurs packages propres aux langues pour rendre un produit complet. Le programme d’installation rassemble les différents packages et effectue les tâches de personnalisation et de maintenance pendant et après l’installation d’Office sur les ordinateurs des utilisateurs. Le Skype pour 2019 Business client utilise des programmes d’installation Click-to-Run.
    
Les rubriques de cette section décrivent comment utiliser et personnaliser le programme d’installation Windows pour déployer le Skype pour client d’entreprise à vos utilisateurs par le biais de vos procédures normales.
  
> [!NOTE]
> Le complément de réunion Skype pour Microsoft Office, qui prend en charge la gestion des réunions dans le client de messagerie et de collaboration Outlook, installe automatiquement avec Skype pour les clients d’entreprise. 
  
> [!NOTE]
> Le programme d’installation d’Office 365 ne désinstalle pas les versions précédentes de Lync. Le Skype pour Business client installe côte à côte avec d’autres clients Lync. 
  
## <a name="installing-windows-clients"></a>Installation des clients Windows

- [Personnaliser l’installation du client Windows dans Skype pour Business Server](customize-windows-client-installation.md)
    
- [Configure the client experience with Skype for Business](configure-the-client-experience.md)
    
- [Configuration de la liste de contacts dynamiques dans Skype Entreprise Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Installation de périphériques clients

- [Skype Entreprise Server 2015 : installation et test de Skype Entreprise pour Windows Phone](windows-phone.md)
    
- [Installation et test de Skype Entreprise pour iOS](ios.md)
    
    
- [Déployer le Lync VDI plug-in avec Skype pour Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [Déployer des clients Web téléchargeables Skype pour Business Server](deploy-web-downloadable-clients.md)
    
- [Personnaliser l'expérience de client Mac dans Skype Entreprise](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Voir aussi

[Déployer le Skype pour client d’entreprise dans Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
