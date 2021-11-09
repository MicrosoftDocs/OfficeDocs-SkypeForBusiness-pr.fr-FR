---
title: Windows PowerShell et Skype Entreprise Server gestion des données
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'Dans Skype Entreprise Server, les outils de gestion sont implémentés à l’aide Windows PowerShell. Windows PowerShell comprend un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet. Skype Entreprise Server outils implémentés à l’Windows PowerShell sont les suivants :'
ms.openlocfilehash: 09726fa35caf569f9f3215b2d3d2217cce3be235
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849707"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell et Skype Entreprise Server gestion des données
 
Dans Skype Entreprise Server, les outils de gestion sont implémentés à l’aide Windows PowerShell. Windows PowerShell comprend un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet. Skype Entreprise Server outils implémentés à l’Windows PowerShell sont les suivants : 
  
- **Générateur de topologie**. Vous utilisez le Générateur de topologie pour créer, ajuster et publier votre topologie planifiée, et il valide votre topologie avant de commencer les installations du serveur. Lorsque vous installez Skype Entreprise Server sur des serveurs individuels, les serveurs lisent la topologie publiée dans le cadre du processus d’installation et le programme d’installation déploie le serveur comme indiqué dans la topologie. Après l’installation, les informations de configuration sont répliquées automatiquement sur tous les serveurs. Les composants peuvent être ajoutés à votre déploiement uniquement à l’aide du Générateur de topologie.
    
- **Skype Entreprise Server Management Shell**. Vous pouvez utiliser Skype Entreprise Server Management Shell pour la gestion complète de la ligne de commande de votre déploiement.
    
- **Skype Entreprise Server panneau de commande**. Vous pouvez utiliser l’interface Skype Entreprise Server’utilisateur du Panneau de Skype Entreprise Server pour gérer les tâches les plus courantes de votre déploiement.
    
Ces outils utilisent des applets de commande Windows PowerShell pour la gestion de votre déploiement, y compris presque 550 applets de commande spécifiques au produit. Les cmdlets de sécurité incluses dans Skype Entreprise Server sont principalement utilisées pour gérer l’authentification, ainsi que les droits et autorisations des utilisateurs. Une large gamme d’applets de commande sont disponibles pour gérer l’authentification, dont certaines pour l’authentification de certificats et de codes confidentiels (PIN). En outre, un certain nombre d’cmdlets vous permettent d’utiliser la nouvelle fonctionnalité de contrôle d’accès Role-Based (RBAC) pour déléguer le contrôle administratif des Skype Entreprise Server. Pour plus d’informations sur les cmdlets Skype Entreprise Server, voir [Skype Entreprise Server Management Shell.](../../manage/management-shell.md)
  
Les fonctionnalités de sécurité des scripts pour Windows PowerShell sont spécialement conçues pour éviter certains problèmes de sécurité liés aux scripts des technologies plus anciennes, notamment Microsoft Visual Basic Scripting Edition (VBScript). Les Windows PowerShell de sécurité sont conçues pour créer un environnement dans lequel les utilisateurs ne peuvent pas exécuter facilement ou sans le savoir des scripts. Par défaut, les Windows PowerShell sécurité de l’utilisateur sont activées. Vous pouvez modifier l’état de ces fonctionnalités pour répondre à vos besoins en matière de scripts et à divers objectifs de sécurité. Cela ne veut pas dire que l’shell empêche les utilisateurs d’exécuter des scripts. Au lieu de cela, il est difficile, par défaut, pour les utilisateurs d’exécuter des scripts sans se rendre compte qu’ils le font. Pour plus d’informations, [voir Windows PowerShell Script Security](/previous-versions/msdn10/gg261722(v=msdn.10)).
