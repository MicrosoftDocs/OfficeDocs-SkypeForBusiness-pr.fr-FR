---
title: Installer l’outil de planification Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Avant de commencer à concevoir et planifier votre infrastructure Skype Entreprise Server 2015 à l’aide de l’outil de planification Skype Entreprise Server 2015, vous devez d’abord installer l’outil de planification. L’outil de planification n’a pas besoin d’être déployé sur une station de travail ou un serveur qui fait partie du domaine ou de l’infrastructure où vous prévoyez d’installer Skype Entreprise Server 2015. Le fichier Lisez-moi qui accompagne l’outil de planification détaille des informations importantes sur l’installation et l’utilisation de l’outil. Certaines informations du fichier Lisez-moi sont dupliquées ici pour plus de clarté.
ms.openlocfilehash: 5d9dc6204647daf03adfab6fcf3cf091d7ba5415
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850887"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Installer l’outil de planification Skype Entreprise Server 2015

Avant de commencer à concevoir et planifier votre infrastructure Skype Entreprise Server 2015 à l’aide de l’outil de planification Skype Entreprise Server 2015, vous devez d’abord installer l’outil de planification. L’outil de planification n’a pas besoin d’être déployé sur une station de travail ou un serveur qui fait partie du domaine ou de l’infrastructure où vous prévoyez d’installer Skype Entreprise Server 2015. Le fichier Lisez-moi qui accompagne l’outil de planification détaille des informations importantes sur l’installation et l’utilisation de l’outil. Certaines informations du fichier Lisez-moi sont dupliquées ici pour plus de clarté.

> [!IMPORTANT]
> L’outil de planification nécessite l’installation par un utilisateur ayant des droits et des autorisations d’administrateur sur l’ordinateur sur lequel l’outil doit être installé.

Les systèmes d’exploitation pris en charge pour l’installation et le fonctionnement de l’outil de planification sont :

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7, édition 32 bits

- Windows édition 7, 64 bits utilisant Windows sur Win32 (WOW)

- Windows Server 2008 R2, à l’aide de WOW

En outre, l’outil de planification nécessite Microsoft .NET Framework 4.5.

Une fois que les conditions de préinstallation sont remplies, vous pouvez installer l’outil de planification.



## <a name="to-install-the-planning-tool"></a>Pour installer l’outil de planification

1. Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.

2. À l Windows’Explorateur ou à une fenêtre de commande, recherchez le répertoire dans lequel vous avez téléchargé les fichiers d’installation de l’outil de planification.

3. Recherchez le SkypeForBusinessPlanningTool.msi. Dans Windows’Explorateur, double-cliquez sur le fichier. Dans la fenêtre de commande, tapez le nom du fichier, puis appuyez sur **Entrée** pour exécuter le fichier.

4. Dans la page d’accueil de **Skype Entreprise Server 2015,** Assistant Configuration de l’outil de planification, cliquez sur **Suivant**.

5. Consultez **le contrat** de licence utilisateur final, sélectionnez J’accepte les termes du contrat de licence si vous choisissez d’accepter les conditions d’utilisation dans le contrat de licence, puis cliquez sur **Suivant**. 

6. Choisissez l’endroit où installer les fichiers de l’outil de planification. L’emplacement par défaut est C:\Program Files (x86)\Skype Entreprise Server 2015\Planning Tool. Si vous souhaitez modifier l’emplacement d’installation, cliquez sur **Modifier.** Sur **Modifier le dossier de destination,** recherchez ou tapez l’emplacement d’installation des fichiers, cliquez sur **OK,** puis sur **Suivant**.

7. Le programme d’installation est maintenant prêt à installer l’outil de planification. Cliquez **sur Installer** pour commencer le processus d’installation.

8. L’installation démarre et la progression s’affiche. Une fois l’installation terminée, cliquez sur **Terminer.**

9. L’outil de planification est prêt à être utilisé.

## <a name="optional-software"></a>Logiciels facultatifs
<a name="Optional_Software"> </a>

L Skype Entreprise Server 2015 Planning Tool est conçu pour exporter vers Microsoft Excel et Microsoft Visio. Bien que ces applications ne soient pas requises pour le fonctionnement de l’outil de planification, elles ajoutent une valeur significative au déploiement et à la documentation de votre conception.

### <a name="microsoft-excel"></a>Microsoft Excel

L’exportation de votre conception vers Microsoft Excel crée un rapport qui affiche sept onglets dans la feuille de calcul :

- Résumé : affiche des informations sur la configuration du site, notamment le nombre d’utilisateurs, les paramètres de capacité et les informations de profil de serveur.

- Profil matériel : affiche un rapport sur les configurations matérielles recommandées pour les serveurs spécifiés dans la topologie, y compris le processeur, la mémoire, le disque et l’interface réseau. La quantité et les spécifications recommandées pour les composants serveur sont également incluses. En outre, chaque serveur est défini par site pour fournir une représentation complète des besoins du serveur par site.

- Configuration requise pour les ports : affiche un rapport de tous les ports activés, ainsi que l’association à l’équilibrage de la charge DNS (Domain Name System) et aux équilibreurs de charge matérielle (HLB). Vous devez utiliser ce rapport pour planifier votre pare-feu et les configurations DNS LB et HLB.

- Rapport de synthèse : affiche le résumé général des paramètres requis pour configurer votre réseau de serveur Edge.

- Rapport sur les certificats : affiche le nom du sujet et les autres noms du sujet requis pour les certificats nécessaires à l’exécution des serveurs Edge.

- Rapport de pare-feu : affiche les ports source et de destination et les adresses IP des interfaces externe et interne.

- Rapport DNS : affiche le nom de domaine complet (FQDN) et les adresses IP/VIP requises pour chaque entrée DNS que vous créez.

### <a name="microsoft-visio"></a>Microsoft Visio

L’exportation de votre conception vers Microsoft Visio crée un diagramme à utiliser dans la documentation de votre topologie et infrastructure configurée. Le diagramme importé peut être modifié et réorganisé pour répondre aux besoins de votre documentation. Un diagramme Visio classique inclut les éléments suivants :

> [!NOTE]
> Si votre conception est suffisamment grande pour nécessiter plus de trois serveurs frontaux, une page supplémentaire est créée pour le pool frontal, les serveurs frontaux, l’ordinateur exécutant SQL Server, les adresses IP et les noms de groupe.

- Topologie globale : diagramme des sites configurés Skype Entreprise Server 2015.

- Onglet Nom du site : affiche la topologie de configuration du site avec le serveur Edge, le pare-feu, le réseau téléphonique commuté (PSTN) avec passerelles et le déploiement de serveur interne. Le déploiement interne se compose de serveurs et de pools configurés, notamment les pools frontaux, les serveurs basés sur SQL Server, les services de domaine Active Directory, les directeurs, les serveurs de messagerie unifiée Exchange, les serveurs de boîtes aux lettres Exchange, les serveurs Office Web Apps, les serveurs de médiation et les serveurs de conversation permanente.

- Diagramme du réseau de périphérie : diagramme détaillant la configuration du serveur Edge avec les adresses IP et les noms de noms de serveur (FQDN) associés. L’équilibrage de charge DNS et les programmes d’équilibrage de la charge matérielle sont également inclus. En outre, les directeurs et le serveur frontal ou le pool frontal sont affichés, avec LB ou HLB DNS associé et l’adresse IP affectée (l’outil de planification prend en charge les adresses IPv4 et IPv6) et le nom deqdn.

## <a name="see-also"></a>Voir aussi
<a name="Optional_Software"> </a>

[Installation de l’outil de planification](/previous-versions/office/lync-server-2013/lync-server-2013-installing-the-planning-tool)