---
title: Utiliser le BPA Analyzer pour rechercher des problèmes potentiels dans votre déploiement
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f787268301570d4440240289c19fdd1e266a607
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a>Utilisation de l’analyseur de meilleures pratiques pour analyser le déploiement de Lync Server 2013 pour détecter des problèmes potentiels

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-21_

Pour exécuter une analyse d’analyse des pratiques recommandées, vous devez spécifier les éléments suivants :

  - **Les informations d’identification**   pour exécuter une analyse, vous devez vous connecter à un ordinateur sur lequel le système d’analyse des recommandations est installé à l’aide d’un compte membre du groupe Administrateurs local. Par ailleurs, vous devez vous connecter à l’aide d’un compte d’utilisateur disposant des droits d’utilisateur et des autorisations nécessaires pour exécuter les analyses appropriées, ou vous devez spécifier des informations d’identification qui disposent des privilèges et autorisations d’utilisateur appropriés lorsque vous exécutez l’analyseur de meilleures pratiques. Pour plus d’informations, consultez la section [appartenances aux groupes et conditions d’utilisation requise pour l’analyseur de meilleures pratiques dans Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).

  - **Étendue de l’analyse**   pour spécifier l’étendue de la numérisation, sélectionnez les catégories et les serveurs que vous souhaitez analyser. Vous pouvez sélectionner toutes les catégories, une ou plusieurs catégories ou un ou plusieurs serveurs au sein d’une catégorie spécifique dans votre environnement Lync Server.

  - **Type de numérisation**   actuellement, le seul type de numérisation disponible est disponible (option activée par défaut). L’analyse de vérification de l’intégrité génère un rapport incluant des erreurs, des avertissements et d’autres informations pour tous les serveurs spécifiés dans l’étendue.

  - ****   Les options de vitesse du réseau à débit de réseau incluent Fast LAN (100 Mbps ou plus), LAN (10 Mbps), WAN rapide (1,5 Mbps) ou WAN (64 kb/s). Le temps estimé pour terminer la numérisation est basé sur ce paramètre. Ce paramètre est également utilisé pour définir le délai d’expiration. Lors de l’analyse, l’analyseur de meilleures pratiques attend la réponse d’un serveur pour une durée spécifiée. S’il ne reçoit pas de réponse dans le délai imparti, il passe au serveur suivant de l’analyse. Sur les réseaux plus lents, ce délai d’expiration spécifié est plus long pour tenir compte des latences du réseau plus longues. Nous vous recommandons de sélectionner le lien le plus lent dans votre topologie pour ce paramètre afin que l’outil ne soit pas trop rapide.

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a>Pour analyser le déploiement de Lync Server 2013

1.  Ouvrez une session sur un ordinateur sur lequel le système d’analyse des recommandations est installé à l’aide d’un compte membre du groupe Administrateurs local et ayant d’autres droits et autorisations d’utilisateur requis.

2.  Cliquez sur **Démarrer**, pointez sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis cliquez sur **recommandations Analyzer**.

3.  Dans l’écran d' **Accueil** , cliquez sur **Sélectionner les options pour une nouvelle analyse**.

4.  Dans la page **se connecter à Active Directory** , vérifiez le nom spécifié dans **Active Directory Server**, puis effectuez l’une des opérations suivantes :
    
      - Pour effectuer une analyse à l’aide des informations d’identification que vous avez utilisées pour vous connecter à l’ordinateur, cliquez sur **se connecter au serveur Active Directory**.
    
      - Pour spécifier d’autres informations d’identification que vous souhaitez utiliser pour les services de domaine Active Directory (AD FS), Edge Server ou Exchange Server, cliquez sur **afficher les options de connexion avancées**, activez chaque case à cocher pour lesquelles des informations d’identification distinctes sont requises, spécifiez les informations d’identification pour chaque case sélectionnée, puis cliquez sur **se connecter au serveur Active Directory**.
    
    <div>
    

    > [!NOTE]
    > Avant de commencer l’analyse, l’analyseur de meilleures pratiques effectue une vérification du réseau et des autorisations pour vérifier que les informations d’identification du compte spécifiées sont valides et que l’analyseur des meilleures pratiques peut se connecter aux services de domaine Active Directory (AD FS). Si l’outil s’exécute sur un serveur de groupe de travail, l’outil vérifie également qu’il peut se connecter aux serveurs Edge du réseau de périmètre (autrement dit, s’il est inclus dans l’analyse).

    
    </div>

5.  Dans la page **Démarrer une nouvelle analyse des meilleures pratiques** , sélectionnez les options que vous voulez inclure dans l’analyse, spécifiez la vitesse du réseau, puis cliquez sur **Démarrer l’analyse**.

6.  Sur la page **analyse terminée** , cliquez sur **afficher un rapport de cette analyse recommandée**.

7.  Dans la page **afficher le rapport** des recommandations, effectuez l’une des opérations suivantes :
    
      - Pour afficher les rapports dans une liste organisée par composant serveur, cliquez sur **rapports de liste**, puis sur l’onglet **tous les problèmes** ou **éléments d’information** .
    
      - Pour afficher les rapports sous forme de liste hiérarchique organisée par type de résultat, cliquez sur **rapports d’arborescence**, puis sur l’onglet **affichage détaillé** ou **affichage de synthèse** .
    
      - Pour afficher d’autres rapports, cliquez sur **autres rapports**.
    
    <div>
    

    > [!NOTE]
    > Pour plus d’informations sur les meilleurs rapports d’analyseurs et les problèmes qu’ils ont identifiés, voir <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">afficher et utiliser les rapports créés par meilleurs analyseurs dans Lync server 2013</A> et <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analyser et résoudre les problèmes identifiés par l’analyseur de meilleures pratiques dans</A>Lync Server 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

