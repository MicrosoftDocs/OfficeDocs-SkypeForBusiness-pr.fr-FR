---
title: Installer l’outil de planification dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Avant de commencer à concevoir et à planifier votre infrastructure 2015 de Skype entreprise Server à l’aide de l’outil de planification de Skype entreprise Server 2015, vous devez d’abord installer l’outil de planification. L’outil de planification n’a pas besoin d’être déployé vers une station de travail ou un serveur qui fait partie de l’infrastructure ou du domaine sur lequel vous envisagez d’installer Skype entreprise Server 2015. Le fichier Lisez-moi fourni avec les détails de l’outil de planification est une information importante sur son installation et son utilisation. Certaines des informations contenues dans le fichier Lisez-moi sont expliquées ici par souci de clarté.
ms.openlocfilehash: 29cadae219faadb68a8a027de11309efc8e3f10b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816383"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Installer l’outil de planification dans Skype Entreprise Server 2015

Avant de commencer à concevoir et à planifier votre infrastructure 2015 de Skype entreprise Server à l’aide de l’outil de planification de Skype entreprise Server 2015, vous devez d’abord installer l’outil de planification. L’outil de planification n’a pas besoin d’être déployé vers une station de travail ou un serveur qui fait partie de l’infrastructure ou du domaine sur lequel vous envisagez d’installer Skype entreprise Server 2015. Le fichier Lisez-moi fourni avec les détails de l’outil de planification est une information importante sur son installation et son utilisation. Certaines des informations contenues dans le fichier Lisez-moi sont expliquées ici par souci de clarté.

> [!IMPORTANT]
> L’outil de planification nécessite une installation par un utilisateur disposant de droits d’administrateur et d’autorisations sur l’ordinateur sur lequel l’outil doit être installé.

Les systèmes d’exploitation pris en charge pour l’installation et l’exécution de l’outil de planification sont les suivants :

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7, édition 32 bits

- Windows 7, édition 64 bits avec WOW (Windows on Win32)

- Windows Server 2008 R2 avec WOW

Par ailleurs, l’outil de planification nécessite Microsoft .NET Framework 4,5.

Après avoir satisfait la configuration requise, vous pouvez ensuite installer l’outil de planification.



## <a name="to-install-the-planning-tool"></a>Pour installer l’outil de planification

1. Connectez-vous à l’ordinateur local en tant que membre du groupe administrateurs.

2. À l’aide de l’Explorateur Windows ou d’une fenêtre de commande, recherchez le répertoire dans lequel vous avez téléchargé les fichiers d’installation de l’outil de planification.

3. Recherchez le fichier SkypeForBusinessPlanningTool.msi. Dans l’Explorateur Windows, double-cliquez sur le fichier. Dans la fenêtre de commande, tapez le nom du fichier, puis appuyez sur **Entrée** pour exécuter le fichier.

4. Dans la page d’accueil de l’**Assistant Configuration de l’outil de planification de Skype Entreprise Server 2015**, cliquez sur **Suivant**.

5. Passez en revue le **Contrat de Licence Utilisateur Final**, sélectionnez **J’accepte les termes du contrat de licence** si vous choisissez d’accepter les termes d’utilisation contenus dans le contrat de licence, puis cliquez sur **Suivant**.

6. Choisissez où vous souhaitez installer les fichiers de l’outil de planification. L’emplacement d’installation par défaut est C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. Si vous souhaitez choisir un autre emplacement, cliquez sur **Modifier**. Dans **Modifier le dossier de destination**, accédez à l’emplacement d’installation des fichiers ou tapez-le directement dans le champ, cliquez sur **OK**, puis sur **Suivant**.

7. Le programme d’installation est désormais prêt à installer l’outil de planification. Cliquez sur **Installer** pour commencer le processus d’installation.

8. L’installation débute et la progression s’affiche. Une fois l’installation terminée, cliquez sur **Terminer**.

9. L’outil de planification est prêt à l’emploi.

## <a name="optional-software"></a>Logiciels facultatifs
<a name="Optional_Software"> </a>

L’outil de planification de Skype entreprise Server 2015 est conçu pour être exporté vers Microsoft Excel et Microsoft Visio. Même si ces applications ne sont pas nécessaires pour l’utilisation de l’outil de planification, elles ajoutent une valeur importante au déploiement et à la documentation de votre conception.

### <a name="microsoft-excel"></a>Microsoft Excel

L’exportation de votre conception vers Microsoft Excel permet de créer un rapport sous forme de feuille de calcul à quatre onglets :

- Résumé : affiche des informations sur la configuration du site, dont le nombre d’utilisateurs, les paramètres de capacité et les informations de profil du serveur.

- Profil matériel-affiche un rapport sur les configurations matérielles recommandées pour les serveurs spécifiés dans la topologie, dont l’UC, la mémoire, le disque et l’interface réseau. La quantité et les caractéristiques conseillées pour les composants serveur y figurent également. Par ailleurs, chaque serveur est défini par site afin de fournir une représentation complète de la configuration serveur requise pour chaque site.

- Configuration requise pour les ports : affiche un rapport de tous les ports activés, ainsi que l’Association au service d’équilibrage de la charge de DNS (Domain Name System) et des équilibreurs de charge matérielle (HLB). Vous devez utiliser ce rapport pour planifier votre pare-feu et les configurations de l’équilibrage de la charge DNS et des programmes d’équilibrage de la charge matérielle.

- Rapport de synthèse : affiche la synthèse générale des paramètres nécessaires à la configuration de votre réseau Edge Server.

- Rapport sur les certificats : affiche le nom du sujet et les noms de domaine alternatif requis pour les certificats nécessaires à l’exécution des serveurs Edge.

- Rapport de pare-feu-affiche les ports et adresses IP sources et de destination pour les interfaces internes et externes.

- Rapport DNS-affiche le nom de domaine complet (FQDN) et les adresses IP/VIP requises pour chaque entrée DNS que vous créez.

### <a name="microsoft-visio"></a>Microsoft Visio

L’exportation de votre conception vers Microsoft Visio crée un diagramme à utiliser dans la documentation de votre topologie et infrastructure configurée. Le diagramme importé peut être modifié et réorganisé pour répondre aux besoins de votre documentation. Un diagramme Visio classique inclut les éléments suivants :

> [!NOTE]
> Si votre conception est suffisamment grande pour nécessiter plus de trois serveurs frontaux, une page supplémentaire est créée pour le pool frontal, les serveurs frontaux, l’ordinateur exécutant SQL Server, les adresses IP et les noms de domaine complets.

- Topologie globale : diagramme des sites 2015 Skype entreprise Server configurés.

- Onglet nom du site : affiche la topologie de configuration de site avec serveur de périmètre, pare-feu, réseau téléphonique public commuté (RTC) avec passerelles et le déploiement de serveur interne. Le déploiement interne se compose de serveurs et de pools configurés, y compris les pools front end, serveurs SQL Server, services de domaine Active Directory, directeurs, serveurs de messagerie unifiée Exchange, serveurs de boîte aux lettres Exchange, serveurs Office Web Apps. Serveurs de médiation et serveurs de chat permanents.

- Diagramme de réseau Edge-schéma de détails de la configuration du serveur de périphérie avec adresses IP et noms de domaine complets associés. L’équilibrage de la charge DNS et les programmes d’équilibrage de la charge matérielle sont également inclus. De plus, les directeurs et le serveur frontal ou le pool frontal sont affichés, avec DNS ou HLB associé et l’adresse IP attribuée (l’outil de planification prend en charge à la fois les adresses IPv4 et IPv6) et le FQDN.

## <a name="see-also"></a>Voir aussi
<a name="Optional_Software"> </a>

[Installing the Planning Tool](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
