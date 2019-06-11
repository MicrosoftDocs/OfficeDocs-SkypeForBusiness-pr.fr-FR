---
title: 'Lync Server 2013: exécuter des cas de test de routage de voix'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cded8f3bf44388103ccf5a33507973817de45ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a>Exécuter des cas de test de routage de voix dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-24_

Vous pouvez exécuter tous les cas de test dans votre suite de tests de routage de voix ou exécuter un ou plusieurs cas de test sélectionnés.

<div>

## <a name="to-run-all-voice-routing-test-cases"></a>Pour exécuter tous les cas de test de routage vocale

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **routage des communications vocales** , puis cliquez sur **tester le routage vocal**.

4.  Dans la page **test de routage vocal** , cliquez sur **action** , puis sur **Tout exécuter**.
    
    Le statut de réussite ou d’échec de chaque cas de test est affiché dans la colonne **passe/échec** . Si un cas de test n’a pas encore été exécuté, N/A s’affiche dans la colonne **passe/échec** .

5.  Facultatif Pour afficher les résultats détaillés pour chaque cas de test, double-cliquez sur le nom du cas de test. Les résultats s’affichent dans la zone ombrée située sur le côté droit de la page **modifier le cas de test** :
    
    1.  **Résultat du test:** État de réussite ou d’échec global du cas de test exécuté.
    
    2.  **Règle de normalisation:** Première règle de normalisation du plan de numérotation sélectionné pour ce cas de test correspondant au numéro composé (valeur du champ **numéro à tester** ).
    
    3.  **Numéro normalisé:** Valeur du numéro composé une fois la règle de normalisation traduite.
    
    4.  **Première utilisation RTC:** Premier enregistrement d’utilisation de réseau téléphonique commuté (PSTN) dans la stratégie vocale sélectionnée pour ce cas de test correspondant au numéro numéroté.
    
    5.  **Premier itinéraire:** Le premier itinéraire vocal dans le premier enregistrement d’utilisation RTC qui correspond au numéro numéroté.
        
        <div>
        

        > [!NOTE]  
        > Les champs <STRONG>enregistrement d’utilisation RTC</STRONG> et <STRONG>route attendue</STRONG> sont facultatifs dans la configuration de cas de test de l’acheminement vocal. Si le cas de test ne spécifie pas ces valeurs, le champ correspondant dans les résultats du test sera vide.

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a>Pour exécuter une ou plusieurs situations de test de routage vocal sélectionnées

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **routage des communications vocales**, puis cliquez sur **tester le routage vocal**.

4.  Dans la page de routage de la **voix** , cliquez sur les noms des cas de test que vous souhaitez exécuter.

5.  Dans le menu **action** , cliquez sur **exécuter la sélection**.
    
    Le statut de réussite ou d’échec de chaque cas de test est affiché dans la colonne **passe/échec** . Si un cas de test n’a pas encore été exécuté, N/A s’affiche dans la colonne **passe/échec** .

6.  Facultatif Pour afficher les résultats détaillés pour chaque cas de test, double-cliquez sur le nom du cas de test. Les résultats s’affichent dans la zone ombrée située sur le côté droit de la page **modifier le cas de test** :
    
    1.  **Résultat du test:** État de réussite ou d’échec global du cas de test exécuté.
    
    2.  **Règle de normalisation:** Première règle de normalisation du plan de numérotation sélectionné pour ce cas de test correspondant au numéro composé (valeur du champ **numéro à tester** ).
    
    3.  **Numéro normalisé:** Valeur du numéro composé une fois la règle de normalisation traduite.
    
    4.  **Première utilisation RTC:** Premier enregistrement d’utilisation RTC dans la stratégie vocale sélectionnée pour ce cas de test correspondant au numéro numéroté.
    
    5.  **Premier itinéraire:** Le premier itinéraire vocal dans le premier enregistrement d’utilisation RTC qui correspond au numéro numéroté.
        
        <div>
        

        > [!NOTE]  
        > Les champs <STRONG>enregistrement d’utilisation RTC</STRONG> et <STRONG>route attendue</STRONG> sont facultatifs dans la configuration de cas de test de l’acheminement vocal. Si le cas de test ne spécifie pas ces valeurs, le champ correspondant dans les résultats du test sera vide.

        
        </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Test du routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)  
[Exécution des tests de routage des communications vocales dans Lync Server 2013](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

