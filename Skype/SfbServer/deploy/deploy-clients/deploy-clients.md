---
title: Déployer des clients pour Skype Entreprise Server
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Résumé : Vue d’ensemble des méthodes d’installation du client d’entreprise pour Skype Entreprise.'
ms.openlocfilehash: d21424d268e6b03e46bfa11b06b7d1929bb015b1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841956"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Déployer des clients pour Skype Entreprise Server
 
**Résumé :** Vue d’ensemble des méthodes d’installation des clients d’Skype Entreprise.
  
La façon dont vous déployez Skype Entreprise pour vos utilisateurs varie selon que vous avez acheté Skype Entreprise dans le cadre d’un plan Microsoft 365 ou Office 365 ou que vous avez acheté une version avec licence en volume de Skype Entreprise. 
  
- **Microsoft 365 ou Office 365** Si vous avez un plan Microsoft 365 ou Office 365 qui inclut Skype Entreprise, la technologie d’installation utilisée est appelée « Click-to-Run ». Vous pouvez laisser vos utilisateurs installer Skype Entreprise eux-mêmes à partir du Centre d'administration Microsoft 365. Vous pouvez également déployer des Skype Entreprise à vos utilisateurs en téléchargeant le logiciel sur votre réseau local, puis en utilisant vos outils de déploiement de logiciels existants, par exemple avec Microsoft Endpoint Configuration Manager. Pour plus d’informations sur l’installation Skype Entreprise qui est livré avec Microsoft 365 et Office 365, voir Déployer le [client Skype Entreprise dans](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)Microsoft 365 ou Office 365 .
    
- **Licence en volume** Si vous avez une version sous licence en volume du client Skype Entreprise 2015 ou 2016, la technologie d’installation utilisée est Windows Installer (MSI). Un package Windows d’installation basé sur le programme d’installation se compose de plusieurs fichiers MSI. Un package MSI principal indépendant de la langue s’accompagne d’un ou plusieurs packages spécifiques à la langue pour en faire un produit complet. Le programme d’installation assemble les packages individuels et effectue des tâches de personnalisation et de maintenance pendant et après l’installation d’Office sur les ordinateurs des utilisateurs. Le client Skype Entreprise 2019 utilise des programme d’installation « En un clic ».
    
Les rubriques de cette section décrivent comment utiliser et personnaliser le programme d’installation Windows pour déployer le client Skype Entreprise à vos utilisateurs via vos procédures normales.
  
> [!NOTE]
> Le Réunion Skype pour Microsoft Office, qui prend en charge la gestion des réunions à partir du client de messagerie et de collaboration Outlook, s’installe automatiquement avec Skype Entreprise clients. 
  
> [!NOTE]
> Les Microsoft 365 et Office 365 programmes d’installation ne désinstallent pas les versions précédentes de Lync. Le Skype Entreprise client s’installe côte à côte avec d’autres clients Lync. 
  
## <a name="installing-windows-clients"></a>Installation de Windows clients

- [Personnaliser Windows’installation du client dans Skype Entreprise Server](customize-windows-client-installation.md)
    
- [Configurer l’expérience client avec Skype Entreprise](configure-the-client-experience.md)
    
- [Configurer la liste de contacts intelligents dans Skype Entreprise Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Installation des clients d’appareil

- [Installer et tester les Skype Entreprise pour Windows Phone](windows-phone.md)
    
- [Installer et tester Skype Entreprise pour iOS](ios.md)
    
    
- [Déployer le plug-in Lync VDI avec Skype Entreprise Server](deploy-the-lync-vdi-plug-in.md)
    
- [Déployer des clients web téléchargeables dans Skype Entreprise Server](deploy-web-downloadable-clients.md)
    
- [Personnaliser l’expérience client Mac dans Skype Entreprise](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Voir aussi

[Déployer le client Skype Entreprise client dans Microsoft 365 ou Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
