---
title: Outils de gestion de Windows PowerShell et de Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'Dans Skype entreprise Server, les outils de gestion sont implémentés à l’aide de Windows PowerShell. Windows PowerShell inclut un environnement de ligne de commande, des commandes spécifiques au produit et un langage de script complet. Les outils Skype entreprise Server implémentés à l’aide de Windows PowerShell incluent les éléments suivants:'
ms.openlocfilehash: 3eb156e002603378ec77fbbcbde4772870aad907
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296881"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Outils de gestion de Windows PowerShell et de Skype entreprise Server
 
Dans Skype entreprise Server, les outils de gestion sont implémentés à l’aide de Windows PowerShell. Windows PowerShell inclut un environnement de ligne de commande, des commandes spécifiques au produit et un langage de script complet. Les outils Skype entreprise Server implémentés à l’aide de Windows PowerShell incluent les éléments suivants: 
  
- **Générateur de topologie**. Le générateur de topologie vous permet de créer, d’ajuster et de publier votre topologie planifiée et de valider votre topologie avant de commencer les installations serveur. Lorsque vous installez Skype entreprise Server sur des serveurs individuels, les serveurs lisent la topologie publiée dans le cadre du processus d’installation, et le programme d’installation déploie le serveur conformément aux instructions de la topologie. After setup, configuration information is automatically replicated to all servers. Components can be added to your deployment only by using Topology Builder.
    
- **Skype entreprise Server Management Shell**. Vous pouvez utiliser Skype entreprise Server Management Shell pour une gestion complète en ligne de commande de votre déploiement.
    
- **Panneau de configuration Skype entreprise Server**. Vous pouvez utiliser l’interface utilisateur du panneau de configuration Skype entreprise Server pour gérer les tâches les plus courantes dans votre déploiement.
    
Ces outils utilisent des cmdlets Windows PowerShell pour la gestion de votre déploiement, y compris des applets de applet 550 spécifiques au produit. Les applets de vérification de sécurité incluses dans Skype entreprise Server servent essentiellement à gérer l’authentification, ainsi que les droits d’utilisateur et les autorisations. Une vaste gamme d’applets de commande est disponible pour gérer l’authentification, dont des applets de commande pour l’authentification de certificats et de codes confidentiels (PIN). De plus, un certain nombre d’applets de commande vous permettent d’utiliser la nouvelle fonctionnalité de contrôle d’accès basée sur un rôle (RBAC) pour déléguer le contrôle d’administration de Skype entreprise Server. Pour plus d’informations sur les applets de connexion Skype entreprise Server, reportez-vous à la rubrique [Skype entreprise Server Management Shell](../../manage/management-shell.md).
  
Les fonctionnalités de sécurité de script pour Windows PowerShell sont spécifiquement conçues pour éviter certains problèmes de sécurité liés au script des technologies plus anciennes, y compris Microsoft Visual Basic Scripting Edition (VBScript). Les fonctionnalités de sécurité de Windows PowerShell sont conçues pour créer un environnement dans lequel les utilisateurs ne peuvent pas facilement exécuter de scripts ou sans le savoir. Par défaut, les fonctionnalités de sécurité de Windows PowerShell sont activées. Vous pouvez modifier l’état de ces fonctionnalités pour les adapter à vos besoins de script et à divers objectifs de sécurité. Cela ne veut pas dire que le shell empêche les utilisateurs d’exécuter des scripts. Mais plutôt, il est plus difficile, par défaut, pour les utilisateurs d’exécuter des scripts sans en avoir conscience. Pour plus d’informations, reportez-vous à la rubrique [sécurité du script Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=213145).
  

