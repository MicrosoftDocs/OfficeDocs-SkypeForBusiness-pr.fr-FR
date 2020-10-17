---
title: 'Lync Server 2013 : création ou modification d’une stratégie d’emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying a location policy
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49733557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f87bf9aff433b70bc50b3fcff209ecd14ea268e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516781"
---
# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a>Création ou modification d’une stratégie d’emplacement dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Dans Lync Server 2013, vous pouvez utiliser la stratégie d’emplacement pour appliquer les paramètres liés à la fonctionnalité Enhanced 9-1-1 (E9-1-1) et aux paramètres de localisation pour les utilisateurs ou les contacts. La stratégie d’emplacement détermine si un utilisateur peut avoir recours au système E9-1-1 et, le cas échéant, le comportement d’un appel d’urgence. Par exemple, la stratégie d’emplacement permet de définir le numéro d’appel d’urgence (par exemple 911 aux États-Unis, 15 en France), de déterminer si le service de sécurité de l’entreprise doit être automatiquement averti et comment l’appel doit être acheminé.

Vous pouvez configurer des stratégies d’emplacement à partir du groupe **Configuration réseau** dans le panneau de configuration Lync Server 2013. Dans le panneau de configuration Lync Server, vous pouvez afficher, créer, modifier ou supprimer des stratégies d’emplacement. Suivez les procédures indiquées dans cette section pour créer ou modifier une stratégie d’emplacement. Pour plus d’informations sur la suppression des stratégies d’emplacement, voir [Suppression d’une stratégie d’emplacement dans Lync Server 2013](lync-server-2013-deleting-a-location-policy.md).

Dans Lync Server 2013, vous pouvez remplacer la durée par défaut entre les demandes des clients pour une mise à jour de l’emplacement à partir du service informations d’emplacement. La valeur par défaut est 4 heures. Utilisez l’applet de commande **Set-CsLocationPolicy** avec le paramètre LocationRefreshInterval pour remplacer la valeur par défaut.

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a>Pour créer une nouvelle stratégie d’emplacement dans le panneau de configuration Lync Server

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie d’emplacement**.

4.  Dans la page **Stratégie d’emplacement**, cliquez sur **Nouveau**, puis sélectionnez le type de stratégie que vous souhaitez créer :
    
      - Pour créer une stratégie de site, cliquez sur **Stratégie du site**. Dans **Sélectionner un site**, choisissez le site auquel vous souhaitez appliquer la stratégie et cliquez sur **OK**. Dans la page **Créer une stratégie d’emplacement**, le champ **Étendue** contient la valeur **Site** et le champ **Nom** contient le nom du site que vous avez choisi. Vous ne pouvez modifier aucun de ces champs. Une stratégie de site est automatiquement appliquée à tous les utilisateurs sur le site spécifié et remplace la stratégie globale qui leur était appliquée.
    
      - Pour créer une **stratégie de l’utilisateur**, cliquez sur **Stratégie de l’utilisateur**. Dans la page **Créer une stratégie d’emplacement**, le champ **Étendue** contient la valeur **Utilisateur**. Vous ne pouvez pas modifier cette valeur. Dans le champ **Nom**, tapez le nom que vous souhaitez donner à cette stratégie. Une stratégie de l’utilisateur ne s’applique pas automatiquement aux utilisateurs. Après avoir créé la stratégie de l’utilisateur, vous devez manuellement octroyer la stratégie aux utilisateurs ou aux sites réseau auxquels vous souhaitez que la stratégie s’applique.

5.  Renseignez les champs restants, comme suit :
    
      - **Activer les services**     d’urgence améliorés Activez cette case à cocher pour activer les utilisateurs associés à cette stratégie pour E9-1-1. Lorsque les services d’urgence sont activés, les clients Lync Server récupèrent les informations d’emplacement lors de l’inscription et incluent ces informations lors d’un appel d’urgence.
    
      - **Emplacement**     Spécifiez l’une des valeurs suivantes :
        
          - **Obligatoire**     L’utilisateur est invité à entrer les informations d’emplacement lorsque le client s’inscrit à un nouvel emplacement. L’utilisateur peut ignorer l’invite sans fournir aucune information. S’il fournit des informations, le fournisseur de services d’urgence répond d’abord à l’appel d’urgence pour vérifier l’emplacement, puis l’appel est transmis à l’opérateur du centre d’appels de la sécurité publique (c’est-à-dire l’opérateur des services d’urgence).
        
          - **Non requis**     L’utilisateur ne sera pas invité à entrer un emplacement. Lorsqu’un appel est effectué sans informations d’emplacement, le fournisseur de services d’urgence y répond et demande qu’un emplacement lui soit indiqué.
        
          - **Exclusion de responsabilité**     Cette option est identique à celle **requise** , sauf que l’utilisateur ne peut pas faire disparaître l’invite sans entrer les informations d’emplacement. L’utilisateur peut toujours appeler les services d’urgence, mais aucun autre appel ne peut être passé sans fournir les informations. De plus, un texte d’exclusion s’affiche pour informer l’utilisateur des conséquences du refus de fournir des informations sur l’emplacement. Pour définir le texte de la clause d’exclusion de responsabilité, vous devez utiliser Lync Server Management Shell pour exécuter la cmdlet **Set-CsLocationPolicy** ou la cmdlet **New-CsLocationPolicy** avec le paramètre EnhancedEmergencyServiceDisclaimer. Pour plus d’informations, reportez-vous à [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) ou [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) dans la documentation Lync Server Management Shell.
            
            <div>
            

            > [!NOTE]  
            > Dans Lync Server 2013, vous pouvez utiliser la stratégie d’emplacement pour définir différentes clauses d’exclusion de responsabilité pour différents paramètres régionaux ou différents ensembles d’utilisateurs, contrairement à Lync Server 2010 où vous pouvez spécifier uniquement une clause d’exclusion de responsabilité globale pour l’ensemble de l’organisation.

            
            </div>
    
      - **Utiliser l’emplacement pour les services d’urgence uniquement**     Lync peut utiliser des informations d’emplacement pour diverses raisons (par exemple, pour avertir les collègues de votre emplacement actuel). Activez cette case à cocher pour que les informations sur l’emplacement soient uniquement disponibles lors d’un appel d’urgence.
    
      - **Utilisation PSTN**     L’utilisation du réseau téléphonique commuté (PSTN) qui sera utilisé pour déterminer l’itinéraire des communications vocales qui sera utilisé pour acheminer les appels d’urgence des clients à l’aide de ce profil. L’itinéraire associé à cette utilisation doit pointer sur une jonction SIP dédiée aux appels d’urgence ou à une passerelle ELIN (Emergency Location Identification Number) qui route les appels d’urgence vers le centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP) le plus proche.
    
      - Numéro de téléphone d' **urgence**     Le numéro composé pour joindre les services d’urgence. Aux États-Unis, cette valeur est 911. La chaîne doit être composée des chiffres 0 à 9 et peut avoir une longueur comprise entre 1 et 10 chiffres.
    
      - Masque de numérotation d' **urgence**     Nombre que vous souhaitez traduire en valeur de la valeur de numéro de téléphone d’urgence lorsqu’il est composé. Par exemple, si vous entrez 212 dans ce champ et si la valeur du champ Numéro d’urgence est 911, le numéro appelé sera le 911 si un utilisateur compose le 212. Cela permet de composer d’autres numéros d’urgence et de pouvoir joindre quand même les services d’urgence (par exemple, si une personne provenant d’un pays où le numéro d’urgence est différent tente de composer ce numéro au lieu du numéro du pays dans lequel elle se trouve actuellement). Vous pouvez définir plusieurs masques d’appel d’urgence en séparant les valeurs par des points-virgules. Par exemple, 212;414. La longueur maximale de la chaîne est 100 caractères. Chaque caractère doit être un chiffre compris entre 0 et 9.
        
        <div>
        

        > [!IMPORTANT]  
        > Assurez-vous que la valeur du masque d’appel n’est pas identique à un numéro figurant dans une plage de numéros d’appels parqués. Le routage du parcage d’appels aura priorité sur la conversion des chaînes d’appel d’urgence. Pour afficher les plages de numéros d’appels parqués, cliquez sur <STRONG>Fonctionnalités vocales</STRONG> dans la barre de navigation de gauche, puis cliquez sur <STRONG>Parcage d’appel</STRONG>. Pour plus d’informations, voir <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">configurer les extensions de numéros de téléphone pour les appels de parking dans Lync Server 2013</A>.

        
        </div>
    
      - **URI**     de notification Un ou plusieurs URI (Uniform Resource Identifier) SIP devant être avertis en cas d’appel d’urgence. Par exemple, le service de sécurité de la société peut être informé via un message instantané chaque fois qu’un appel d’urgence est effectué. Si l’emplacement de l’appelant est disponible, celui-ci sera inclus dans la notification. Plusieurs URI SIP peuvent être insérés dans une liste dans laquelle ils sont séparés par des virgules. Par exemple, « sip:security@litwareinc.com »,« sip:kmyer@litwareinc.com ». Les listes de distribution sont prises en charge. La chaîne doit comporter entre 1 et 256 caractères et commencer par le préfixe « sip: ». Avant que vous ne cliquiez dans le champ URI de notification un exemple est affiché.
    
      - **URI**     de conférence L’URI SIP, dans ce cas le numéro de téléphone, d’un tiers qui fera l’appel à des appels d’urgence. Par exemple, le service de sécurité de l’entreprise peut recevoir un appel l’invitant à écouter ou à participer à un appel d’urgence (en fonction de la valeur fournie dans le champ **Mode conférence**). La chaîne doit comporter entre 1 et 256 caractères et commencer par le préfixe sip:. Un exemple est affiché avant que vous ne cliquiez dans ce champ.
    
      - **Mode conférence**     Si vous spécifiez une valeur dans le champ **URI de conférence** , le **mode conférence** détermine si un tiers peut participer à l’appel ou s’il peut uniquement écouter. Spécifiez une des options suivantes :
        
          - **Unidirectionnel**     Un tiers peut uniquement écouter la conversation entre l’appelant et l’opérateur PSAPI.
        
          - **Bidirectionnel**     Un tiers peut écouter et participer à l’appel entre l’appelant et l’opérateur PSAPI.

6.  Cliquez sur **Valider**.
    
    <div>
    

    > [!IMPORTANT]  
    > Lorsque vous créez une stratégie utilisateur, cette stratégie ne s’applique initialement à aucun utilisateur ou site réseau. Pour appliquer la stratégie à un utilisateur, cliquez sur <STRONG>Utilisateurs</STRONG> dans la barre de navigation de gauche. Recherchez l’utilisateur auquel vous souhaitez appliquer la stratégie. Dans le menu <STRONG>Edition</STRONG>, cliquez sur <STRONG>Afficher les détails</STRONG>. Dans la page <STRONG>Modifier l’utilisateur Lync Server</STRONG>, sélectionnez la nouvelle stratégie d’emplacement dans la liste déroulante <STRONG>Stratégie d’emplacement</STRONG>, puis cliquez sur <STRONG>Valider</STRONG>.<BR>Pour appliquer la stratégie à un site réseau, cliquez sur <STRONG>Configuration réseau</STRONG> dans la barre de navigation de gauche et cliquez sur <STRONG>Site</STRONG>. Recherchez le site réseau auquel vous souhaitez appliquer la stratégie. Dans le menu <STRONG>Edition</STRONG>, cliquez sur <STRONG>Afficher les détails</STRONG>. Dans <STRONG>Modifier le site</STRONG>, sélectionnez la nouvelle stratégie d’emplacement dans la liste déroulante <STRONG>Stratégie d’emplacement</STRONG>, puis cliquez sur <STRONG>Valider</STRONG>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a>Pour modifier une stratégie d’emplacement dans le panneau de configuration Lync Server

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie d’emplacement**.

4.  Dans la page **Stratégie d’emplacement**, sélectionnez la stratégie d’emplacement que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier la stratégie d’emplacement**, modifiez les champs comme il convient (pour plus d’informations, voir l’étape 5 dans la procédure de création d’une stratégie d’emplacement plus haut dans cette rubrique).

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Suppression d’une stratégie d’emplacement dans Lync Server 2013](lync-server-2013-deleting-a-location-policy.md)  


[Définition de la stratégie d’emplacement pour Lync Server 2013](lync-server-2013-defining-the-location-policy.md)  


[Configurer les extensions de numéros de téléphone pour les appels de parking dans Lync Server 2013](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

