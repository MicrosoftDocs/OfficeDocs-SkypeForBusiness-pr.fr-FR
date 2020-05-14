---
title: Déployer des clients pour Skype entreprise Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Résumé : vue d’ensemble des méthodes d’installation des clients d’entreprise pour Skype entreprise.'
ms.openlocfilehash: 8d6e59582c3c420d5752a84f793e6c3025b3c500
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220644"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Déployer des clients pour Skype entreprise Server
 
**Résumé :** Vue d’ensemble des méthodes d’installation des clients d’entreprise pour Skype entreprise.
  
Le mode de déploiement de Skype entreprise pour vos utilisateurs dépend de si vous avez acheté Skype entreprise dans le cadre d’un plan Microsoft 365 ou Office 365 ou si vous avez acheté une version de licence en volume de Skype entreprise. 
  
- **Microsoft 365 ou Office 365** Si vous disposez d’un plan Microsoft 365 ou Office 365 incluant Skype entreprise, la technologie d’installation utilisée est appelée « démarrer en un clic ». Vous pouvez autoriser vos utilisateurs à installer Skype entreprise pour eux-mêmes à partir du centre d’administration Microsoft 365. Vous pouvez aussi déployer Skype entreprise auprès de vos utilisateurs en téléchargeant le logiciel sur votre réseau local, puis en utilisant vos outils de déploiement de logiciels existants, tels que le gestionnaire de configuration de point de terminaison Microsoft. Pour obtenir des informations sur l’installation de Skype entreprise qui est fournie avec Microsoft 365 et Office 365, consultez [la rubrique deploy the Skype for Business client in Microsoft 365 ou office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Licence en volume** Si vous disposez d’une version sous licence en volume du client Skype entreprise 2015 ou 2016, la technologie d’installation utilisée est Windows Installer (MSI). Un package d’installation basé sur Windows Installer se compose de plusieurs fichiers MSI. Un package MSI principal indépendant de la langue s’accompagne d’un ou plusieurs packages spécifiques à la langue pour en faire un produit complet. Le programme d’installation assemble les packages individuels et effectue des tâches de personnalisation et de maintenance pendant et après l’installation d’Office sur les ordinateurs des utilisateurs. Le client Skype entreprise 2019 utilise des programmes d’installation « démarrer en un clic ».
    
Les rubriques de cette section décrivent comment utiliser et personnaliser Windows Installer pour déployer le client Skype entreprise pour vos utilisateurs par le biais de vos procédures normales.
  
> [!NOTE]
> Le complément réunion Skype pour Microsoft Office, qui prend en charge la gestion des réunions à partir du client de messagerie et de collaboration Outlook, s’installe automatiquement avec les clients Skype entreprise. 
  
> [!NOTE]
> Les programmes d’installation de Microsoft 365 et Office 365 ne désinstalle pas les versions précédentes de Lync. Le client Skype entreprise s’installe côte à côte avec d’autres clients Lync. 
  
## <a name="installing-windows-clients"></a>Installation des clients Windows

- [Personnaliser l’installation du client Windows dans Skype entreprise Server](customize-windows-client-installation.md)
    
- [Configuration de l’expérience client avec Skype entreprise](configure-the-client-experience.md)
    
- [Configurer la liste de contacts dynamiques dans Skype entreprise Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Installation de clients d’appareils

- [Installer et tester Skype entreprise pour Windows Phone](windows-phone.md)
    
- [Installation et test de Skype entreprise pour iOS](ios.md)
    
    
- [Déployer le plug-in Lync VDI avec Skype entreprise Server](deploy-the-lync-vdi-plug-in.md)
    
- [Déploiement de clients Web téléchargeables dans Skype entreprise Server](deploy-web-downloadable-clients.md)
    
- [Personnaliser l’expérience client Mac dans Skype entreprise](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Voir aussi

[Déployer le client Skype entreprise dans Microsoft 365 ou Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
