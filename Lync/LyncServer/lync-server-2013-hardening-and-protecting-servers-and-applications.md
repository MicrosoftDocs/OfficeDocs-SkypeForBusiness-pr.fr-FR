---
title: 'Lync Server 2013 : renforcement et protection des serveurs et des applications'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b0a6179e77e4688693fe277748a8933a9dbe911
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a>Renforcement et protection des serveurs et des applications pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-12-05_

Vous devez renforcer et protéger votre système d’exploitation et vos applications conformément aux meilleures pratiques pour ce composant spécifique. Cette section décrit comment renforcer les serveurs d’applications et utiliser la stratégie de groupe pour implémenter les verrouillages de sécurité.

<div>


> [!NOTE]  
> Vous pouvez également renforcer et protéger les bases de données utilisées pour le déploiement de Microsoft Lync Server 2013. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-hardening-and-protecting-databases.md">la rubrique renforcement et protection des bases de données de Lync Server 2013</A>.



</div>

<div>

## <a name="securing-application-servers"></a>Sécurisation des serveurs d’applications

Pour les serveurs d’applications, le système d’exploitation et l’application doivent être renforcés. Par exemple, un ordinateur Windows Server 2008 dédié à l’exécution de Microsoft Internet Security and Acceleration (ISA) Server 2006 doit être renforcé à partir du système d’exploitation et du point de vue de l’application. La réduction du nombre de services en cours d’exécution et fournis par le serveur doit être un objectif principal.

</div>

<div>

## <a name="securing-virtual-servers"></a>Sécurisation des serveurs virtuels

Les captures instantanées de serveur virtuel contiennent des copies des disques de données du serveur et contiennent également des dumps de données en mémoire, qui peuvent contenir des données de chiffrement sensibles susceptibles de conduire à des attaques. Pour les serveurs de production implémentés à l’aide de la virtualisation, vous devez désactiver toutes les captures instantanées de serveur ou les gérer de manière très contrôlée. Pour plus d’informations sur la sécurisation des serveurs virtuels Hyper-V, voir le Guide de [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176)sécurité Hyper-v à l’adresse suivante :.

</div>

<div>

## <a name="group-policy"></a>Stratégie de groupe

Dans Windows Server 2008 et Windows Server 2008 R2, la stratégie de groupe fournit la gestion de la configuration de bureau basée sur l’annuaire. Vous pouvez utiliser la stratégie de groupe pour implémenter les verrouillages de sécurité en définissant les paramètres ordinateur et utilisateur dans un objet de stratégie de groupe (GPO) pour les éléments suivants :

  - Stratégies basées sur le registre

  - Sécurité

  - Installation de logiciels

  - Scripts

  - Redirection de dossiers

  - Services d’installation à distance

Pour fournir une interface utilisateur permettant à l’administrateur de configurer ces paramètres, les modèles d’administration sont fournis avec les versions du système d’exploitation, les versions des service packs et certaines applications, y compris Lync Server 2013.

Le fichier Communicator. adm est un modèle d’administration fourni avec Lync Server 2013, est installé dans le répertoire% windir%\\INF\\ et fournit une interface aux paramètres de la stratégie de groupe. Chaque paramètre de Communicator. adm correspond à un paramètre dans le Registre qui affecte le comportement de l’application.

Les paramètres sont accessibles à partir de GPedit. dll, qui est disponible à partir de la console utilisateurs et ordinateurs Active Directory et de la console de gestion des stratégies de groupe (GPMC).

</div>

<div>

## <a name="group-policy-security-settings"></a>Paramètres de sécurité de la stratégie de groupe

La stratégie de groupe contient les paramètres de sécurité d’un objet GPO sous Configuration de l’ordinateur/Paramètres Windows/paramètres de sécurité lors de l’accès à partir de GPedit. dll. Vous pouvez importer des modèles de sécurité pour configurer les paramètres de sécurité de l’objet de stratégie de groupe. Le Guide de sécurité de Windows Server [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) 2008 à l’adresse et le kit de gestion de la [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) conformité de la sécurité de Windows Server 2008 R2, accessible à l’aide de ces modèles, que vous pouvez modifier pour répondre à vos besoins.

</div>

<div>

## <a name="best-practices"></a>Meilleures pratiques

  - Renforcer tous les systèmes d’exploitation et applications du serveur.

  - Protégez les captures instantanées de serveur et améliorez la sécurité de tous les serveurs virtuels.

  - Utiliser la stratégie de groupe pour implémenter les verrouillages de sécurité.

</div>

</div>

<span> </span>

</div>

</div>

</div>

