---
title: 'Lync Server 2013 : configuration de Lync Server 2013 pour qu’il fonctionne avec la messagerie unifiée sur Microsoft Exchange Server'
description: 'Lync Server 2013 : configurez Lync Server 2013 pour qu’il fonctionne avec la messagerie unifiée sur Microsoft Exchange Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05ef2902ffc03b14e04b378a2ef18e03c8c58372
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578040"
---
# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>Configurer Lync Server 2013 pour qu’il fonctionne avec la messagerie unifiée sur Microsoft Exchange Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

_**Dernière modification de la rubrique :** 2013-04-03_

Cette étape nécessite l’utilitaire d’intégration de la messagerie unifiée Exchange (OcsUmUtil.exe)). Cet outil se trouve sur le serveur Lync Server 2013 dans le.. \\ Fichiers communs des fichiers programme \\ \\ dossier de \\ prise en charge de Microsoft Lync Server 2013.

<div>

## <a name="running-the-exchange-um-integration-utility"></a>Exécution de l’utilitaire d’intégration de la messagerie unifiée Exchange

L’utilitaire d’intégration de la messagerie unifiée Exchange doit être exécuté à partir d’un compte d’utilisateur présentant les caractéristiques suivantes :

  - l’appartenance aux groupes RTCUniversalServerAdmins et RtcUniversalUserAdmins (comprenant l’autorisation de lecture des paramètres de la messagerie unifiée Exchange Server) ;

  - Droits d’utilisateur au sein du domaine pour créer des objets contact dans le conteneur d’unités d’organisation spécifié.

Lorsque vous exécutez l’utilitaire d’intégration de la messagerie unifiée Exchange, il exécute les tâches suivantes :

  - Il créé des objets contact pour chaque numéro de standard automatique et numéro d’accès d’abonné dont les utilisateurs de Voix Entreprise se serviront.

  - Vérifie que le nom de chaque plan de numérotation voix entreprise correspond au contexte téléphonique du plan de numérotation de messagerie unifiée correspondant. Cette correspondance est nécessaire uniquement si le plan de numérotation de messagerie unifiée est exécuté sur une version d’Exchange *antérieure* à Exchange 2010 Service Pack 1 (SP1).

> [!IMPORTANT]
> Avant d’exécuter l’utilitaire d’intégration de la messagerie unifiée Exchange, assurez-vous que vous avez réalisé les opérations suivantes :
> <ul>
> <li><p>Créez un ou plusieurs plans de numérotation de messagerie unifiée Exchange, comme décrit dans la documentation du produit Exchange.</p>
> <p>Pour Microsoft Exchange Server 2010, consultez &quot; la rubrique créer un plan de numérotation de messagerie unifiée &quot; à l’adresse <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a> .</p>
> <p>Pour Microsoft Exchange Server 2007 Service Pack 1 (SP1), consultez &quot; la rubrique How to Create a Unified Messaging SIP URI SIP dial plan &quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a> .</p></li>
> <li><p>Créez un ou plusieurs plans de numérotation Lync Server correspondants, comme décrit dans <a href="lync-server-2013-create-a-dial-plan.md">Create a dial plan in Lync Server 2013</a>.</p></li>
> <ul><li>Si vous utilisez une version d’Exchange antérieure à Microsoft Exchange Server 2010 SP1, vous devez entrer le nom de domaine complet (FQDN) du plan de numérotation SIP de messagerie unifiée Exchange correspondant dans le champ <STRONG>nom simple</STRONG> du plan de numérotation de Lync Server 2013. Si vous utilisez Microsoft Exchange Server 2010 SP1 ou le Service Pack le plus récent, cette correspondance de nom de plan de numérotation n’est pas nécessaire.</li></ul>
> <li>Créez un standard automatique et assurez-vous que le numéro d’accès abonné et le numéro du standard automatique sont au format E.164.</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>Pour exécuter l’utilitaire d’intégration de la messagerie unifiée Exchange

1.  Sur un serveur frontal, ouvrez une invite de commandes et tapez **cd% COMMONPROGRAMFILES% \\ Microsoft Lync Server 2013 \\ support**, puis appuyez sur entrée.

2.  Tapez **OcsUmUtil.exe**, puis appuyez sur Entrée.

3.  Cliquez sur **Charger les données** pour rechercher toutes les forêts Exchange approuvées.

4.  Dans la liste **Plans de numérotation SIP**, sélectionnez un plan de numérotation SIP de messagerie unifiée pour lequel vous souhaitez créer des objets contact, puis cliquez sur **Ajouter**.

5.  Dans la zone **Contact**, acceptez l’unité d’organisation par défaut, ou cliquez sur **Parcourir** pour démarrer le **Sélecteur d’unités d’organisation**. Dans la zone **Sélecteur d’unités d’organisation**, sélectionnez une unité d’organisation et cliquez sur **OK**. Vous pouvez aussi cliquer sur **Créer une unité d’organisation** pour créer une unité d’organisation sous la racine, ou toute autre unité d’organisation dans le domaine (par exemple, « OU=RTC Special Accounts,DC=fourthcoffee,DC=com »), puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Le nom unique de l’unité d’organisation que vous avez sélectionnée ou créée est désormais affiché dans la zone <STRONG>Unité d’organisation</STRONG>.

    
    </div>

6.  Dans la zone **Nom**, acceptez le nom de plan de numérotation par défaut, ou tapez un nouveau nom complet pour l’objet contact que vous créez.
    
    <div>
    

    > [!NOTE]  
    > Par exemple, si vous créez un objet contact d’accès abonné, vous pouvez tout simplement le nommer Accès Abonné.

    
    </div>

7.  Dans la zone **Adresse SIP**, acceptez l’adresse SIP par défaut ou tapez une nouvelle adresse SIP.
    
    <div>
    

    > [!NOTE]  
    > Si vous tapez une nouvelle adresse SIP, elle doit commencer par <STRONG>SIP:</STRONG> (c’est-à-dire, « SIP: » le signe : compris).

    
    </div>

8.  Dans la liste **serveur ou pool** , sélectionnez le serveur Standard Edition ou le pool frontal dans lequel l’objet contact doit être activé.
    
    <div>
    

    > [!NOTE]  
    > Il est préférable de choisir le pool où les utilisateurs activés pour Voix Entreprise et la messagerie unifiée Exchange sont déployés.

    
    </div>

9.  Dans la liste **Numéro de téléphone**, sélectionnez **Entrez le numéro de téléphone** ou **Utilisez ce numéro pilote à partir d’Exchange UM**, puis entrez un numéro de téléphone.

10. Dans la liste **Type de contact**, sélectionnez le type de contact que vous souhaitez créer, puis cliquez sur **OK**.

11. Répétez les étapes 1 à 10 pour les objets contact supplémentaires que vous souhaitez créer.
    
    <div>
    

    > [!NOTE]  
    > Vous devez créer au moins un contact pour chaque standard automatique. Si vous souhaitez un accès externe, vous devez également créer un contact d’accès abonné et spécifier des numéros SDA (Sélection directe à l’arrivée).

    
    </div>

</div>

Pour vérifier que les objets contact ont bien été créés, ouvrez Utilisateurs et ordinateurs Active Directory et sélectionnez l’unité d’organisation dans laquelle les objets ont été créés. Les objets contact apparaissent dans le volet d’informations.

</div>

</div>

<span> </span>

</div>

</div>

</div>

