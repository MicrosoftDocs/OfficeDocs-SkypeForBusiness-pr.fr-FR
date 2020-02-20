---
title: 'Lync Server 2013 : exécuter des cas de test de routage des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bb8cb857460e233fe8f277cfabee382ff2a9ebd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a>Exécuter des cas de test de routage des communications vocales dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-24_

Vous pouvez exécuter tous les cas de test dans votre suite de cas de test de routage des communications vocales, ou vous pouvez exécuter un ou plusieurs cas de test sélectionnés.

<div>

## <a name="to-run-all-voice-routing-test-cases"></a>Pour exécuter tous les cas de test de routage des communications vocales

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Tester le routage des communications vocales**.

4.  Sur la page **Tester le routage des com. vocales**, cliquez sur **Action** puis sur **Exécuter tout**.
    
    Le statut de réussite ou d’échec de chaque cas de test apparaît dans la colonne **Réussite/échec**. Si un cas de test n’a pas encore été exécuté, la colonne **Réussite/échec** contient la mention N/A.

5.  (Facultatif) Pour consulter les résultats détaillés de chaque cas de test, double-cliquez sur le nom du cas de test. Les résultats apparaissent dans la zone ombrée sur le côté droit de la page **Modifier le cas de test** :
    
    1.  **Résultat du test :** État de réussite ou d’échec global du cas de test exécuté.
    
    2.  **Règle de normalisation :** Première règle de normalisation du plan de numérotation sélectionné pour ce cas de test et qui correspond au numéro composé (valeur du champ **nombre à tester** ).
    
    3.  **Numéro normalisé :** Valeur du numéro composé une fois la règle de normalisation traduite.
    
    4.  **Première utilisation PSTN :** Premier enregistrement d’utilisation du réseau téléphonique commuté (PSTN) dans la stratégie de voix sélectionnée pour ce cas de test et qui correspond au numéro composé.
    
    5.  **Première route :** Premier itinéraire de communications vocales dans le premier enregistrement d’utilisation PSTN correspondant au numéro composé.
        
        <div>
        

        > [!NOTE]  
        > Les champs <STRONG>Enregistrement d’utilisation PSTN attendu</STRONG> et <STRONG>Itinéraire attendu</STRONG> sont facultatifs dans la configuration d’un cas de test de routage des communications vocales. Si les cas de test ne spécifient pas ces valeurs, le champ correspondant dans les résultats de test sera vide.

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a>Pour exécuter un ou plusieurs cas de test de routage des communications vocales

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Tester le routage des communications vocales**.

4.  Sur la page **Tester le routage des com. vocales**, cliquez sur le nom des cas de test que vous souhaitez exécuter.

5.  Dans le menu **Action**, cliquez sur **Exécuter la sélection**.
    
    Le statut de réussite ou d’échec de chaque cas de test apparaît dans la colonne **Réussite/échec**. Si un cas de test n’a pas encore été exécuté, la colonne **Réussite/échec** contient la mention N/A.

6.  (Facultatif) Pour consulter les résultats détaillés de chaque cas de test, double-cliquez sur le nom du cas de test. Les résultats apparaissent dans la zone ombrée sur le côté droit de la page **Modifier le cas de test** :
    
    1.  **Résultat du test :** État de réussite ou d’échec global du cas de test exécuté.
    
    2.  **Règle de normalisation :** Première règle de normalisation du plan de numérotation sélectionné pour ce cas de test et qui correspond au numéro composé (valeur du champ **nombre à tester** ).
    
    3.  **Numéro normalisé :** Valeur du numéro composé une fois la règle de normalisation traduite.
    
    4.  **Première utilisation PSTN :** Premier enregistrement d’utilisation PSTN dans la stratégie de voix sélectionnée pour ce cas de test qui correspond au numéro composé.
    
    5.  **Première route :** Premier itinéraire de communications vocales dans le premier enregistrement d’utilisation PSTN correspondant au numéro composé.
        
        <div>
        

        > [!NOTE]  
        > Les champs <STRONG>Enregistrement d’utilisation PSTN attendu</STRONG> et <STRONG>Itinéraire attendu</STRONG> sont facultatifs dans la configuration d’un cas de test de routage des communications vocales. Si les cas de test ne spécifient pas ces valeurs, le champ correspondant dans les résultats de test sera vide.

        
        </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Tester le routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)  
[Exécution des tests de routage des communications vocales dans Lync Server 2013](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

