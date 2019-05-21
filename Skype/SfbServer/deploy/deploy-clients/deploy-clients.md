---
title: Déploiement de clients pour Skype entreprise Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Résumé: vue d’ensemble des méthodes d’installation du client d’entreprise pour Skype entreprise.'
ms.openlocfilehash: df9ac5356c05001df09168ca619ffc200b35ea4f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282443"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Déploiement de clients pour Skype entreprise Server
 
**Résumé:** Vue d’ensemble des méthodes d’installation du client d’entreprise pour Skype entreprise.
  
Le mode de déploiement de Skype entreprise pour vos utilisateurs dépend de la manière dont vous avez acheté Skype entreprise dans le cadre d’une offre Office 365 ou si vous avez acheté une version sous licence en volume de Skype entreprise. 
  
- **Office 365** Si vous avez un plan Office 365 incluant Skype entreprise, la technologie d’installation qui est utilisée est appelée démarrer en un clic. Grâce à Office 365, vous pouvez permettre aux utilisateurs d’installer Skype entreprise pour eux-mêmes à partir du portail Office 365. Vous pouvez aussi déployer Skype entreprise pour vos utilisateurs en téléchargeant le logiciel sur votre réseau local, puis en utilisant vos outils de déploiement de logiciels existants, tels que Microsoft System Center Configuration Manager. Pour plus d’informations sur l’installation de Skype entreprise qui est fourni avec Office 365, voir [déployer le client Skype entreprise dans office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Licence en volume** Si vous disposez d’une version sous licence en volume du client Skype entreprise 2015 ou 2016, la technologie d’installation qui est utilisée est le programme d’installation Windows (MSI). Un package d’installation basé sur Windows Installer comporte plusieurs fichiers MSI. Un package MSI de base indépendant de la langue est associé à un ou plusieurs packages spécifiques à la langue pour créer un produit complet. La configuration assemble les packages individuels et effectue des tâches de personnalisation et de maintenance pendant et après l’installation d’Office sur les ordinateurs des utilisateurs. Le client Skype entreprise 2019 utilise des programmes de installation «démarrer en un clic».
    
Les rubriques de cette section expliquent comment utiliser et personnaliser Windows Installer pour déployer le client Skype entreprise auprès de vos utilisateurs dans le cadre de vos procédures normales.
  
> [!NOTE]
> Le complément réunion Skype pour Microsoft Office, qui prend en charge la gestion de la réunion à partir du client de messagerie et de collaboration Outlook, s’installe automatiquement avec les clients Skype entreprise. 
  
> [!NOTE]
> Le programme d’installation d’Office 365 ne désinstalle pas les versions précédentes de Lync. Le client Skype entreprise est installé côte à côte avec d’autres clients Lync. 
  
## <a name="installing-windows-clients"></a>Installation de clients Windows

- [Personnaliser l’installation du client Windows dans Skype entreprise Server](customize-windows-client-installation.md)
    
- [Configure the client experience with Skype for Business](configure-the-client-experience.md)
    
- [Configuration de la liste de contacts dynamiques dans Skype Entreprise Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Installation de clients d’appareils

- [Skype Entreprise Server 2015 : installation et test de Skype Entreprise pour Windows Phone](windows-phone.md)
    
- [Installation et test de Skype Entreprise pour iOS](ios.md)
    
    
- [Déploiement du plug-in Lync VDI avec Skype entreprise Server](deploy-the-lync-vdi-plug-in.md)
    
- [Déploiement de clients Web à télécharger dans Skype entreprise Server](deploy-web-downloadable-clients.md)
    
- [Personnaliser l'expérience de client Mac dans Skype Entreprise](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Voir aussi

[Déploiement du client Skype entreprise dans Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
