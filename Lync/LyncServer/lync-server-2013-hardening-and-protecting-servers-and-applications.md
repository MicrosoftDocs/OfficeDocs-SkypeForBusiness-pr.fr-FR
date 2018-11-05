---
title: 'Lync Server 2013 : renforcement et protection des serveurs et des applications'
TOCTitle: Renforcement et protection des serveurs et des applications pour Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn518331(v=OCS.15)
ms:contentKeyID: 60484503
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Renforcement et protection des serveurs et des applications pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Vous devez renforcer et protéger votre système d’exploitation et vos applications en respectant les meilleures pratiques pour le composant en question. Cette section décrit comment renforcer les serveurs d’applications et utiliser une stratégie de groupe pour mettre en œuvre des verrous de sécurité.

> [!NOTE]  
> Vous pouvez également renforcer et protéger les bases de données utilisées pour votre déploiement Microsoft Lync Server 2013. Pour plus d’informations, reportez-vous à la section <a href="lync-server-2013-hardening-and-protecting-databases.md">Renforcement et protection des bases de données de Lync Server 2013</a>.

## Sécurisation des serveurs d’applications

Pour les serveurs d’applications, il est nécessaire de renforcer le système d’exploitation et l’application. Par exemple, un ordinateur Windows Server 2008 dédié à l’exécution de Microsoft Internet Security and Acceleration (ISA) Server 2006 doit être renforcé à partir du système d’exploitation et du point de vue de l’application. La réduction du nombre de services exécutés et fournis par le serveur doit être l’objectif principal.

## Sécurisation des serveurs virtuels

Les instantanés du serveur virtuel contiennent des copies des disques de données du serveur ainsi que des vidages des données en mémoire, qui peuvent tous deux comporter des données de chiffrement sensibles pouvant conduire à des attaques. Pour les serveurs de production mis en œuvre à l’aide de la virtualisation, vous devez désactiver tous les instantanés de serveur ou les gérer de façon très contrôlée. Pour plus d’informations sur la sécurisation des serveurs virtuels Hyper-V, reportez-vous au manuel de sécurité Hyper-V, sous [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176).

## Stratégie de groupe

Dans Windows Server 2008 et Windows Server 2008 V2, une stratégie de groupe permet de gérer la configuration du bureau basée sur l’annuaire. Vous pouvez utiliser une stratégie de groupe pour mettre en œuvre des verrous de sécurité en définissant les paramètres de l’ordinateur et de l’utilisateur dans un objet stratégie de groupe (GPO) pour les éléments suivants :

  - Stratégies basées sur le registre

  - Sécurité

  - Installation du logiciel

  - Scripts

  - Redirection du dossier

  - Services d’installation à distance

Pour que l’administrateur dispose d’une interface utilisateur pour configurer ces paramètres, des modèles d’administration sont fournis avec les versions de système d’exploitation, les versions de Service Pack et certaines applications, dont Lync Server 2013.

Le fichier Communicator.adm est un modèle d’administration fourni avec Lync Server 2013, installé dans le répertoire *%windir%*\\inf\\, qui fournit une interface pour les paramètres de la stratégie de groupe. Chaque paramètre dans le fichier Communicator.adm correspond à un paramètre dans le registre, qui affecte le comportement de l’application.

Les paramètres sont accessibles à partir de GPedit.dll, qui est disponible à partir de la console Utilisateurs et ordinateurs Active Directory et la console de gestion des stratégies de groupe.

## Paramètres de sécurité des stratégies de groupe

La stratégie de groupe contient des paramètres de sécurité pour un objet stratégie de groupe dans Configuration de l’ordinateur/Paramètres Windows/Paramètres de sécurité lors de l’accès à GPedit.dll. Vous pouvez importer des modèles de sécurité pour configurer des paramètres de sécurité pour l’objet stratégie de groupe. Le manuel de sécurité Windows Server 2008 sous [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) et la boîte à outils de gestion de la conformité à la sécurité de Windows Server 2008 V2 sous [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) contiennent différents exemples de modèle que vous pouvez modifier pour répondre à vos besoins.

## Meilleures pratiques

  - Renforcez l’ensemble des systèmes d’exploitation et des applications.

  - Protégez les instantanés de serveur et améliorez la sécurité de tous les serveurs virtuels.

  - Utilisez la stratégie de groupe pour mettre en œuvre des verrous de sécurité.

