---
title: Créer ou modifier un ensemble de paramètres de configuration de réunion
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a5f80066a68b45e062a351478bea93a5c2e8fd0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Créer ou modifier un ensemble de paramètres de configuration de réunion dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Vous pouvez utiliser les paramètres de la page Configuration de la réunion pour définir diverses caractéristiques de l’utilisation de la réunion. Par défaut, les paramètres globaux définissent l’interface de participation. Vous pouvez également créer des paramètres de participation à une réunion au niveau du site et du pool. Si vous créez des paramètres au niveau du pool, ceux-ci s’appliquent à toutes les réunions hébergées par ce pool. Si vous ne créez pas de paramètres au niveau du pool, les paramètres définis au niveau du site s’appliquent, s’ils existent. Si aucun paramètre n’a été défini au niveau du site, les paramètres globaux s’appliquent à l’ensemble des réunions.

<div>

## <a name="to-create-new-meeting-join-settings"></a>Pour créer des paramètres de participation à une réunion

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence** , puis sur Configuration de la **réunion**.

4.  Dans la page **Configuration de la réunion**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :
    
      - Pour créer une stratégie au niveau du site, cliquez sur **Configuration du site**. Dans le champ de recherche **Sélectionner un site**, tapez le nom du site (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des sites obtenus, cliquez sur le site voulu, puis sur **OK**.
    
      - Pour créer une stratégie au niveau du pool, cliquez sur **Configuration du pool**. Dans le champ de recherche **Sélectionner un service**, tapez le nom du service de pool (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des services obtenus, cliquez sur le pool de votre choix, puis sur **OK**.

5.  Pour acheminer les participants qui appellent à partir du réseau téléphonique commuté (RTC) via la salle d’attente, désactivez la case à cocher **Les appelants RTC ignorent la salle d’attente**. Par défaut, les participants qui appellent d’un réseau RTC accèdent directement à la réunion.

6.  Pour désigner le présentateur de la réunion, dans **Désigné comme présentateur**, effectuez l’une des opérations suivantes :
    
      - Pour n’autoriser que l’organisateur à être présentateur, cliquez sur **Aucun**.
    
      - Pour n’autoriser que les participants membres de votre entreprise à être présentateur, cliquez sur **Société**. Il s’agit du paramètre par défaut.
    
      - Pour autoriser tous les participants à être présentateur, cliquez sur **Tout le monde**.

7.  Pour permettre à l’organisateur de sélectionner un type de conférence lors de la planification d’une réunion, désactivez la case à cocher **Type de conférence affecté par défaut**. Par défaut, le type de conférence est affecté automatiquement.

8.  Pour empêcher les utilisateurs anonymes (non identifiés) d’être automatiquement admis, désactivez la case à cocher **Admettre les utilisateurs anonymes par défaut**. Par défaut, les utilisateurs anonymes sont automatiquement admis aux réunions.

9.  Pour personnaliser l’invitation à la réunion envoyée aux participants, procédez comme suit. Notez que la longueur maximale des URL et du texte de pied de page personnalisé est de 1 Ko. Sauf pour l’**URL de l’aide**, si vous ne spécifiez pas une valeur pour les personnalisations, elles ne seront pas incluses dans la réunion. Si vous n’incluez pas d’URL d’aide personnalisée, l’URL d’aide par défaut pour Lync s’affichera dans l’invitation.
    
      - Pour personnaliser le logo qui figure sur l’invitation à la réunion, dans **URL du logo**, entrez l’emplacement du logo.
        
        <div>
        

        > [!NOTE]
        > Le logo doit être une image GIF ou JPG d’une taille de 188 x 30 pixels.

        
        </div>
    
      - Pour personnaliser le texte d’aide qui figure sur l’invitation à la réunion, dans **URL de l’aide**, entrez l’emplacement du texte d’aide.
    
      - Pour personnaliser les informations légales qui figurent sur l’invitation à la réunion, dans **URL des informations légales**, entrez l’emplacement des informations légales.
    
      - Pour personnaliser le texte de pied de page qui figure sur l’invitation à la réunion, dans **Texte de pied de page personnalisé**, entrez le texte.

10. Cliquez sur **Valider**.

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a>Pour modifier une collection existante de configurations de réunion

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence** , puis sur Configuration de la **réunion**.

4.  Dans la liste des configurations de réunion, cliquez sur la configuration à modifier, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la configuration de la réunion**, modifiez les paramètres de configuration, à l’exception du nom de configuration qui ne peut pas être modifié.

6.  Cliquez sur **Valider**.

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Création de nouveaux paramètres de configuration de réunion à l’aide d’applets de cmdlet Windows PowerShell

Il est possible de créer des paramètres de configuration de réunion (à l’étendue du site uniquement) à l’aide de Windows PowerShell et de l’applet de nouvelle cmdlet New-CsMeetingConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a>Pour créer des paramètres de configuration de réunion qui utilisent les valeurs par défaut

  - Cette commande crée un ensemble de paramètres de configuration de réunion pour le site de Redmond :
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    Comme aucun paramètre (autre que le paramètre d’identité obligatoire) n’est spécifié dans la commande précédente, les nouveaux paramètres de configuration de réunion utiliseront les valeurs par défaut pour toutes ses propriétés.

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a>Pour modifier une valeur de propriété lors de la création des paramètres de configuration de réunion

  - Pour créer des paramètres qui utilisent différentes valeurs de propriété, incluez simplement le paramètre et la valeur de paramètre appropriés. Par exemple, pour créer une collection de paramètres de configuration de réunion qui, par défaut, admet tout le monde à une réunion comme présentateur, utilisez une commande semblable à la suivante :
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a>Pour modifier plusieurs valeurs de propriétés lors de la création des paramètres de configuration de réunion

  - Vous pouvez modifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande admet tout le monde dans une réunion en tant que présentateur et force les utilisateurs RTC à patienter dans la salle d’attente jusqu’à ce qu’ils soient officiellement admis à la réunion :
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de [nouvelle-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

