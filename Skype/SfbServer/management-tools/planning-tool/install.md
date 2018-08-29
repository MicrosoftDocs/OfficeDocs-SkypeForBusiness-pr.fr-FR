---
title: Installer l’outil de planification dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Avant de commencer la conception et planification de votre Skype pour Business Server 2015 infrastructure à l’aide de la Skype pour l’outil de planification de 2015 Business Server, vous devez d’abord installer l’outil de planification. L’outil de planification ne doit pas être déployé sur une station de travail ou un serveur faisant partie de l’infrastructure ou le domaine où vous prévoyez d’installer Skype pour Business Server 2015. Le fichier Readme qui accompagne l’outil de planification des détails des informations importantes sur l’installation et à l’aide de l’outil. Certaines des informations contenues dans le fichier Lisez-moi sont expliquées ici par souci de clarté.
ms.openlocfilehash: 2314a9ae548bea70bc13872714ae3215d7439eec
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244322"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Installer l’outil de planification dans Skype Entreprise Server 2015

Avant de commencer la conception et planification de votre Skype pour Business Server 2015 infrastructure à l’aide de la Skype pour l’outil de planification de 2015 Business Server, vous devez d’abord installer l’outil de planification. L’outil de planification ne doit pas être déployé sur une station de travail ou un serveur faisant partie de l’infrastructure ou le domaine où vous prévoyez d’installer Skype pour Business Server 2015. Le fichier Readme qui accompagne l’outil de planification des détails des informations importantes sur l’installation et à l’aide de l’outil. Certaines des informations contenues dans le fichier Lisez-moi sont expliquées ici par souci de clarté.

> [!IMPORTANT]
> L’outil de planification doit être installé par un utilisateur disposant de droits d’administrateur et des autorisations sur l’ordinateur sur lequel l’outil doit être installé.

Les systèmes d’exploitation pris en charge pour l’installation et l’utilisation de l’outil de planification sont les suivants :

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7, édition 32 bits

- Windows 7, édition 64 bits avec WOW (Windows on Win32)

- Windows Server 2008 R2 avec WOW

En outre, l’outil de planification nécessite Microsoft .NET Framework 4.5.

Une fois que les conditions de préinstallation sont remplies, vous pouvez ensuite installer l’outil de planification.



## <a name="to-install-the-planning-tool"></a>Pour installer l’outil de planification

1. Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.

2. À l’aide de l’Explorateur Windows ou une fenêtre de commande, recherchez le répertoire où vous avez téléchargé les fichiers d’installation de l’outil de planification.

3. Recherchez le fichier SkypeForBusinessPlanningTool.msi. Dans l’Explorateur Windows, double-cliquez sur le fichier. Dans la fenêtre de commande, tapez le nom du fichier, puis appuyez sur **Entrée** pour exécuter le fichier.

4. Dans la page d’accueil de l’**Assistant Configuration de l’outil de planification de Skype Entreprise Server 2015**, cliquez sur **Suivant**.

5. Passez en revue le **Contrat de Licence Utilisateur Final**, sélectionnez **J’accepte les termes du contrat de licence** si vous choisissez d’accepter les termes d’utilisation contenus dans le contrat de licence, puis cliquez sur **Suivant**.

6. Choisissez où vous souhaitez installer les fichiers de l’outil de planification. L’emplacement d’installation par défaut est C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. Si vous souhaitez choisir un autre emplacement, cliquez sur **Modifier**. Dans **Modifier le dossier de destination**, accédez à l’emplacement d’installation des fichiers ou tapez-le directement dans le champ, cliquez sur **OK**, puis sur **Suivant**.

7. Le programme d’installation est maintenant prêt à installer l’outil de planification. Cliquez sur **Installer** pour commencer le processus d’installation.

8. L’installation débute et la progression s’affiche. Une fois l’installation terminée, cliquez sur **Terminer**.

9. L’outil de planification est prêt à être utilisé.

## <a name="optional-software"></a>Optional Software
<a name="Optional_Software"> </a>

Le Skype pour l’outil de planification de Business Server 2015 conçu pour l’exportation vers Microsoft Excel et Microsoft Visio. Alors que ces applications ne sont pas nécessaires au fonctionnement de l’outil de planification, ils ajoutent une valeur significative pour le déploiement et la documentation de votre conception.

### <a name="microsoft-excel"></a>Microsoft Excel

L’exportation de votre conception vers Microsoft Excel permet de créer un rapport sous forme de feuille de calcul à quatre onglets :

- Résumé - affiche des informations sur la configuration du site, notamment le nombre d’utilisateurs, les paramètres de la capacité et les informations de profil de serveur.

- Profil matériel - affiche un rapport sur les configurations matérielle recommandée pour les serveurs qui sont spécifiés dans la topologie, y compris l’interface réseau, la mémoire, disque et processeur. La quantité et les caractéristiques conseillées pour les composants serveur y figurent également. Par ailleurs, chaque serveur est défini par site afin de fournir une représentation complète de la configuration serveur requise pour chaque site.

- Configuration requise des ports - affiche un rapport de tous les ports qui sont activés et l’association (DNS kg) d’équilibrage de charge de système de nom de domaine et les équilibreurs de charge matérielle (HLB). Vous devez utiliser ce rapport pour planifier votre pare-feu et les configurations de l’équilibrage de la charge DNS et des programmes d’équilibrage de la charge matérielle.

- Rapport de synthèse - affiche le récapitulatif des paramètres qui sont nécessaires pour configurer votre réseau de serveur de transport Edge.

- Rapport de certificats - affiche le nom du sujet et les autres noms du sujet qui sont requis pour les certificats nécessaires pour obtenir les serveurs de périphérie en cours d’exécution.

- Rapport - affiche la source et destination des ports et adresses IP des interfaces interne et externe du pare-feu.

- Rapport DNS - affiche le nom de domaine complet (FQDN) et les adresses IP/adresse IP virtuelle est requis pour chaque entrée DNS que vous créez.

### <a name="microsoft-visio"></a>Microsoft Visio

L’exportation de votre conception vers Microsoft Visio crée un diagramme à utiliser dans la documentation de votre topologie et infrastructure configurée. Le diagramme importé peut être modifié et réorganisé pour répondre aux besoins de votre documentation. Un diagramme Visio classique inclut les éléments suivants :

> [!NOTE]
> Si votre conception est suffisante pour demander de plus de trois serveurs frontaux, une page supplémentaire sera créée pour le pool frontal, serveurs frontaux, l’ordinateur qui exécute SQL Server, les adresses IP et noms de domaine complets.

- Topologie globale : diagramme de Skype configuré pour les sites Business Server 2015.

- Onglet Nom de site - affiche la topologie de configuration de site avec le serveur de périphérie, le pare-feu, public switched téléphone PSTN (réseau) avec les passerelles et le déploiement du serveur interne. Déploiement interne se compose de serveurs configurés et pools pools, y compris le serveur frontal, les serveurs SQL Server, Services de domaine Active Directory, directeurs, la messagerie unifiée Exchange (MU) serveurs, les serveurs de boîtes aux lettres Exchange, serveurs Office Web Apps Server, Serveurs de médiation et serveurs de conversation permanente.

- Edge organigramme - diagramme décrivant la configuration du serveur Edge avec associé à des adresses IP et noms de domaine complets. L’équilibrage de la charge DNS et les programmes d’équilibrage de la charge matérielle sont également inclus. En outre, les directeurs et le pool frontal ou serveur frontal sont affichés, avec kg de DNS associé ou matérielle et l’adresse IP (l’outil de planification prend en charge les adresses IPv4 et IPv6) et le nom de domaine complet.

## <a name="see-also"></a>Voir aussi
<a name="Optional_Software"> </a>

[Installation de l’outil de planification](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)