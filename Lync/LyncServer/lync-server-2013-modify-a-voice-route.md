---
title: 'Lync Server 2013 : modifier un itinéraire des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6e2a3f255a77d7773d24d654c5c207b59b887bc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515341"
---
# <a name="modify-a-voice-route-in-lync-server-2013"></a>Modifier un itinéraire des communications vocales dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Cette rubrique explique comment modifier un itinéraire des communications vocales. Pour créer un itinéraire, voir [créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).

<div>

## <a name="to-modify-a-voice-route"></a>Pour modifier un itinéraire de communications vocales

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Itinéraire**.

4.  Dans la page **Itinéraire**, utilisez l’une des méthodes suivantes pour modifier un itinéraire de communications vocales :
    
      - Sélectionnez un nom d’itinéraire de communications vocales, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
      - Sélectionnez un nom d’itinéraire de communications vocales, cliquez sur **Modifier**, puis sur **Copier** et enfin sur **Coller**. Sélectionnez la copie de l’itinéraire de communications vocales créée à l’instant, cliquez sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans la page **Modifier l’itinéraire de communications vocales**, dans le champ **Nom**, tapez un nom descriptif pour l’itinéraire de communications vocales.

6.  (Facultatif) Dans le champ **Description**, tapez une description supplémentaire du nouvel itinéraire de communications vocales.

7.  Pour spécifier les modèles que cet itinéraire doit prendre en charge, vous pouvez générer une expression régulière à l’aide de l’outil **Créer un modèle à suivre**, ou l’écrire manuellement.
    
      - Pour utiliser l’outil **Créer un modèle à suivre** afin de générer une expression régulière, entrez les valeurs comme suit. Vous pouvez spécifier deux types de correspondance de modèles :
        
          - **Chiffres de départ pour les nombres que vous souhaitez autoriser :** Entrez les valeurs de préfixe que cet itinéraire doit prendre en charge (y compris le +, le cas échéant). Par exemple, tapez **+ 425** , puis cliquez sur **Ajouter**. Répétez cette opération pour chaque valeur de préfixe que vous souhaitez inclure dans l’itinéraire.
        
          - **Exceptions :** Si vous souhaitez spécifier une ou plusieurs exceptions pour une valeur de préfixe, mettez en surbrillance le préfixe et cliquez sur **exceptions**. Tapez une ou plusieurs valeurs pour les modèles correspondants que vous ne voulez *pas* que cet itinéraire s’intègre. Par exemple, pour exclure les nombres commençant par + 425237 de l’itinéraire, entrez une valeur de **+ 425237** dans le champ **exceptions** , puis cliquez sur **OK**.
    
      - Pour définir le modèle de correspondance manuellement, cliquez sur **Modifier** dans l’outil **Créer un modèle à suivre**, puis saisissez une expression régulière .NET Framework afin de spécifier le modèle de correspondance pour les numéros de téléphone de destination auxquels l’itinéraire est appliqué. Pour plus d’informations sur la façon d’écrire des expressions régulières, voir « .NET Framework regular expressions » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .

8.  Sélectionnez **Supprimer l’ID** de l’appelant si vous ne souhaitez pas que l’ID du téléphone soit l’ID du destinataire de l’appel sortant. Si vous sélectionnez cette option, vous devez spécifier un **Autre ID de l’appelant** qui apparaîtra sur l’affichage de l’ID d’appelant du destinataire.

9.  Pour associer une ou plusieurs jonctions RTC (réseau téléphonique commuté) à l’itinéraire des communications vocales, cliquez sur **Ajouter**, puis sélectionnez une jonction dans la liste.
    
    <div>
    

    > [!NOTE]  
    > Si votre déploiement inclut des serveurs de médiation Microsoft Office Communications Server 2007 R2, ils seront également disponibles dans la liste.

    
    </div>

10. Pour associer une ou plusieurs utilisations RTC à l’itinéraire des communications vocales, cliquez sur **Sélectionner** et choisissez un enregistrement dans la liste des enregistrements d’utilisation RTC qui ont été définis pour votre déploiement de voix entreprise.
    
    <div>
    

    > [!NOTE]  
    > Pour afficher les propriétés de chacun des enregistrements d’utilisation RTC disponibles, reportez-vous à la rubrique <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage Records in Lync Server 2013</A>.<BR>Pour créer ou modifier des enregistrements d’utilisation RTC, reportez-vous à <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">créer une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync server 2013</A> ou <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013</A>.

    
    </div>

11. Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez le nom de l’enregistrement, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    <div>
    

    > [!NOTE]  
    > Contrairement à une stratégie de voix dans laquelle l’ordre dans lequel sont répertoriés les enregistrements d’utilisation RTC est important, l’ordre des enregistrements d’utilisation RTC dans un itinéraire des communications vocales est insignifiant. Il est toutefois recommandé d’organiser la liste par fréquence d’utilisation, par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Lync Server parcourt la liste du haut vers le bas.)

    
    </div>

12. (Facultatif) Tapez une valeur dans le champ **Entrez un numéro traduit à tester** et cliquez sur **OK**. Les résultats du test sont affichés sous le champ.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez enregistrer un itinéraire de communications vocales qui ne réussit pas encore le test, puis le reconfigurer par la suite. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-test-voice-routing.md">test de routage des communications vocales dans Lync Server 2013</A>.

    
    </div>

13. Cliquez sur **OK**.

14. Dans la page **Itinéraire**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    <div>
    

    > [!NOTE]  
    > Chaque fois que vous créez ou modifiez un itinéraire des communications vocales, vous devez exécuter la commande <STRONG>valider tout</STRONG> pour publier la modification de la configuration. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Afficher les enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Création d’une stratégie de voix et configuration des enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Publier les modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Tester le routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

