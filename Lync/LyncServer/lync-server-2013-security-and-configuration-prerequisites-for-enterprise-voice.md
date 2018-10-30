---
title: "Lync Server 2013 : Cond. Prér. de conf. et de sécurité pour Voix Entreprise"
TOCTitle: Conditions prérequises de configuration et de sécurité pour Voix Entreprise
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398221(v=OCS.15)
ms:contentKeyID: 49296355
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conditions prérequises de configuration et de sécurité pour Voix Entreprise dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-18_

Vérifiez que votre infrastructure est conforme aux conditions préalables suivantes en matière de sécurité, de configuration utilisateur et de matériel pour des scénarios spécifiques.

## Droits d’administration et infrastructure de certificats

Assurez-vous que votre environnement est configuré avec les groupes d’administrateurs et l’infrastructure de certificats suivants à utiliser au cours du processus de déploiement de Voix Entreprise.

  - Les administrateurs déployant Voix Entreprise doivent être membres du groupe RTCUniversalServerAdmins.

  - Les administrateurs doivent disposer des droits appropriés pour effectuer les tâches de configuration :
    
      - **CsVoiceAdministrator :** Ce rôle permet à l’administrateur d’effectuer des tâches de configuration vocale, de gérer les applications vocales et d’affecter des stratégies vocales aux utilisateurs finaux.
    
      - **CsUserAdministrator :** Ce rôle permet à l’administrateur de gérer les propriétés des utilisateurs, par exemple, pour activer Voix Entreprise pour un utilisateur. Ce rôle permet également à l’administrateur d’affecter des stratégies par utilisateur, à l’exception de la stratégie d’archivage, et de gérer les téléphones de partie commune et les périphériques analogues.
    
      - **CsAdministrator :** Ce rôle permet à l’utilisateur d’effectuer toutes les tâches des rôles CsVoiceAdministrator et CsUserAdministrator.
    
    > [!NOTE]  
    > La délégation permet à davantage d’administrateurs de participer au déploiement de Lync Server, sans accès inutile aux ressources.

  - L’infrastructure MKI (Managed Key Infrastructure) est déployée et configurée, à l’aide d’une infrastructure d’autorité de certification Microsoft ou tierce.
    
    > [!NOTE]  
    > Pour plus d’informations sur les certificats requis dans Lync Server, reportez-vous à <a href="lync-server-2013-certificate-infrastructure-requirements.md">Configuration requise pour les infrastructures de certificat pour Lync Server 2013</a> dans la documentation de planification.

## Configuration utilisateur

Si vous avez coIocalisé le serveur de médiation avec chaque pool frontal ou serveur Standard Edition au cours du déploiement des pools frontaux, les paramètres utilisateur nécessaires pour Voix Entreprise ont été configurés automatiquement au cours de l’installation des fichiers pour ces rôles serveur.

Si vous procédez à un nouveau déploiement de la charge de travail de Voix Entreprise, avant de commencer le processus de déploiement, désignez un numéro de téléphone principal pour chaque utilisateur pour lequel vous envisagez d’activer Voix Entreprise. En tant qu’administrateur, vous devez vous assurer que ce numéro est unique. Avant l’implémentation, tous les numéros de téléphones principaux doivent être normalisés (c’est-à-dire correctement formés) et copiés dans la propriété **URI de ligne** de chaque utilisateur à l’aide du Panneau de configuration Lync Server.

> [!NOTE]  
> Pour obtenir des exemples des numéros de téléphone principaux requis pour le déploiement de Voix Entreprise, reportez-vous à la section <a href="lync-server-2013-dial-plans-and-normalization-rules.md">Plans de numérotation et règles de normalisation dans Lync Server 2013</a> de <a href="lync-server-2013-dial-plans-and-normalization-rules.md">Plans de numérotation et règles de normalisation dans Lync Server 2013</a> dans la documentation de planification.

## Étapes suivantes : installer les fichiers ou configurer la connectivité RTC

Après avoir vérifié que les logiciels requis sont disponibles et que votre environnement répond aux conditions préalables pour le déploiement de Voix Entreprise, vous pouvez utiliser le contenu suivant pour :

  - Installer le serveur de médiation comme il est indiqué dans [Installation des fichiers du serveur de médiation dans Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), mais seulement si vous souhaitez déployer un serveur de médiation ou un pool autonome, car les serveurs de médiation sont installés au cours du processus de déploiement du pool frontal ou du serveur Standard Edition lorsqu’ils sont colocalisés avec ces derniers.

  - Ou, commencer à configurer les paramètres pour acheminer les appels pour les utilisateurs de Voix Entreprise, comme il est indiqué dans [Configuration des jonctions dans Lync Server 2013](lync-server-2013-configuring-trunks.md).

