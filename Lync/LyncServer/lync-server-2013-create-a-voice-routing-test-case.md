---
title: 'Lync Server 2013 : création d’un cas de test de routage des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9fac6f65d1bb1c04b8d8597454df775f8545d2a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a>Créer un cas de test de routage des communications vocales dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-07_

<div>

## <a name="to-create-a-test-case"></a>Pour créer un cas de test

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Tester le routage des communications vocales**.

4.  Dans la page **Routage des communications vocales**, cliquez sur **Nouveau** pour créer un nouveau cas de test.

5.  Dans **Nom**, tapez un nom unique pour le cas de test.
    
    Le nom doit être unique parmi tous les cas de test de routage des communications vocales dans votre déploiement Voix Entreprise. Il peut comporter jusqu’à 32 caractères et peut contenir des caractères alphanumériques, outre la barre oblique inverse (\\), le point (.) ou le trait de soulignement (\_).

6.  Dans **Numéro composé à tester**, tapez le numéro composé que vous souhaitez utiliser pour tester la configuration du routage que vous spécifiez pour ce cas de test. À partir du plan de numérotation, de l’itinéraire et de la stratégie de voix, ce numéro sera normalisé et affiché en sortie.

7.  Dans la liste **Plan de numérotation**, sélectionnez le plan de numérotation à utiliser lors de l’exécution du test. Le plan de numérotation global est utilisé par défaut.

8.  Dans la liste **Stratégie de la voix**, sélectionnez la stratégie de voix à utiliser lors de l’exécution du test. La stratégie de voix globale est utilisée par défaut.

9.  Dans **Traduction attendue**, tapez le numéro de téléphone au format dans lequel vous souhaitez le visualiser après la traduction. Il s’agit de la valeur du numéro de téléphone que vous testez une fois qu’il a été traduit par la première règle de normalisation qui correspond dans le plan de numérotation sélectionné. Quand vous exécutez le cas de test, si le numéro que vous testez ne correspond pas à la valeur contenue dans **Traduction attendue** le test échoue.

10. (Facultatif) Dans la liste **Utilisation PSTN attendue**, vous pouvez sélectionner l’enregistrement d’utilisation PSTN devant être utilisé quand vous exécutez le cas de test, en fonction de la stratégie de voix et du plan de numérotation spécifiés. Si un autre enregistrement d’utilisation PSTN est utilisé, le test échoue.

11. (Facultatif) Dans la liste **Itinéraire attendu**, vous pouvez sélectionner l’itinéraire des communications vocales devant être utilisé lorsque vous exécutez le cas de test, en fonction de la stratégie de voix et du plan de numérotation spécifiés. Si un autre itinéraire des communications vocales est utilisé, le test échoue.

12. (Facultatif) Cliquez sur **Exécuter** pour exécuter le cas de test. Les résultats apparaissent dans le panneau droit de la page.

13. Cliquez sur **OK**.

14. Cliquez sur **Valider**, puis sur **Valider tout**.
    
    <div>
    

    > [!NOTE]  
    > Chaque fois que vous créez un cas de test de routage des communications vocales, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de la configuration. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.

    
    </div>
    
    Si le plan de numérotation employé dans le test normalise les numéros de téléphone commençant par un signe plus (par exemple, + 12065551219), cette planification peut entraîner l’échec du test de routage des communications vocales. (Le plan de numérotation et l’itinéraire des communications vocales fonctionneront ; en fait, test-CsDialPlan réussira. Toutefois, le test de routage des communications vocales peut échouer.) Il s’agit d’une information à garder à l’esprit lors du test des itinéraires des communications vocales.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Exporter des cas de test de routage des communications vocales dans Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
[Importer des cas de test de routage des communications vocales dans Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  


[Configuration des plans de numérotation dans Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Configuration des stratégies de voix, des enregistrements d’utilisation RTC et des itinéraires des communications vocales dans Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

