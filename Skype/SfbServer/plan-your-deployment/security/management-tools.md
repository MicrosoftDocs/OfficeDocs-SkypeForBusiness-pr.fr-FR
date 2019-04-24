---
title: Windows PowerShell et Skype pour les outils de gestion de serveur d’entreprise
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'Dans Skype pour Business Server, les outils de gestion sont implémentées à l’aide de Windows PowerShell. Windows PowerShell inclut un environnement de ligne de commande, des commandes spécifiques au produit et un langage de script complet. Skype pour les outils Business Server qui sont implémentées à l’aide de Windows PowerShell sont les suivants :'
ms.openlocfilehash: 743823e5465d6fa18f46d0f8f38802098416d7e6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213591"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell et Skype pour les outils de gestion de serveur d’entreprise
 
Dans Skype pour Business Server, les outils de gestion sont implémentées à l’aide de Windows PowerShell. Windows PowerShell inclut un environnement de ligne de commande, des commandes spécifiques au produit et un langage de script complet. Skype pour les outils Business Server qui sont implémentées à l’aide de Windows PowerShell sont les suivants : 
  
- **Le Générateur de topologie**. Vous utilisez le Générateur de topologie pour créer, modifier et publier votre topologie planifiée, puis il valide votre topologie avant de commencer les installations de serveurs. Lorsque vous installez Skype pour Business Server sur des serveurs individuels, les serveurs de lecture de la topologie publiée dans le cadre du processus d’installation et le programme d’installation déploie le serveur comme indiqué dans la topologie. After setup, configuration information is automatically replicated to all servers. Components can be added to your deployment only by using Topology Builder.
    
- **Skype pour Business Server Management Shell**. Vous pouvez utiliser Skype pour Business Server Management Shell pour la gestion complète de la ligne de commande de votre déploiement.
    
- **Skype pour le panneau de configuration serveur Business**. Vous pouvez utiliser la Skype pour l’interface utilisateur Business Server Control Panel pour gérer les tâches les plus courantes dans votre déploiement.
    
Ces outils utilisent des applets de commande Windows PowerShell pour la gestion de votre déploiement, notamment près 550 applets de commande spécifiques au produit. Les applets de commande de sécurité incluses dans Skype pour Business Server sont principalement utilisées pour gérer l’authentification et les autorisations et droits d’utilisateur. Une vaste gamme d’applets de commande est disponible pour gérer l’authentification, dont des applets de commande pour l’authentification de certificats et de codes confidentiels (PIN). En outre, un nombre de cmdlets permettre la nouvelle fonctionnalité de contrôle d’accès basé sur un rôle (RBAC) permet de déléguer le contrôle administratif de Skype pour Business Server. Pour plus d’informations sur la Skype pour les applets de commande Business Server, voir [Skype pour Business Server Management Shell](../../manage/management-shell.md).
  
Les fonctionnalités de sécurité de script pour Windows PowerShell sont spécifiquement conçues pour éviter certains problèmes de sécurité liés au script des technologies plus anciennes, y compris Microsoft Visual Basic Scripting Edition (VBScript). Les fonctionnalités de sécurité de Windows PowerShell sont destinées à créer un environnement dans lequel les utilisateurs ne peuvent pas facilement ou sans le savoir exécuter des scripts. Par défaut, les fonctionnalités de sécurité de Windows PowerShell sont activées. Vous pouvez modifier l’état de ces fonctionnalités pour les adapter à vos besoins de script et à divers objectifs de sécurité. Cela ne veut pas dire que le shell empêche les utilisateurs d’exécuter des scripts. Mais plutôt, il est plus difficile, par défaut, pour les utilisateurs d’exécuter des scripts sans en avoir conscience. Pour plus d’informations, voir [Sécurité de Script Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=213145).
  

