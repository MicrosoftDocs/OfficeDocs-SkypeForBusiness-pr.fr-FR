---
title: Définition et configuration d’un pool frontal ou d’un serveur Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 847aeda66657b2bd665964d6fec3276dc22807ea
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531511"
---
# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a>Définition et configuration d’un pool frontal ou d’un serveur Standard Edition dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-08_

Pour effectuer cette procédure, il n’est pas nécessaire d’appartenir à un groupe d’administrateurs local ou de domaines privilégiés. Vous devez simplement ouvrir une session sur un ordinateur en tant qu’utilisateur standard.

Si vous déployez un serveur d’entreprise, un nombre minimal de serveurs frontaux dans un pool doit être en cours d’exécution en permanence. Le tableau suivant résume ces exigences :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre total de serveurs frontaux dans le pool</th>
<th>Nombre de serveurs devant s’exécuter pour que le pool soit opérationnel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1-2</p></td>
<td><p>0,1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>n°2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>7-8</p></td>
<td><p>4 </p></td>
</tr>
<tr class="odd">
<td><p>9-10</p></td>
<td><p>5 </p></td>
</tr>
<tr class="even">
<td><p>11-12</p></td>
<td><p>6 </p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Pour Lync Server 2013, chaque fois que vous ajoutez ou supprimez un serveur frontal du pool, vous devez redémarrer les services. La suppression et l’ajout de serveurs doivent être effectuées séparément. Par exemple, si vous envisagez d’ajouter deux serveurs frontaux et de supprimer deux serveurs frontaux, procédez comme suit : 
> <OL>
> <LI>
> <P>Supprimez les deux serveurs frontaux.</P>
> <LI>
> <P>Publiez et réactivez la topologie.</P>
> <LI>
> <P>Redémarrez les services.</P>
> <LI>
> <P>Ajoutez les deux serveurs frontaux.</P>
> <LI>
> <P>Publiez et réactivez la topologie.</P>
> <LI>
> <P>Redémarrez les services.</P></LI></OL>



</div>

Une fois que vous avez défini votre topologie, utilisez la procédure suivante pour définir un pool frontal pour votre site. Pour plus d’informations sur la définition de la topologie, reportez-vous à la rubrique [define and Configure a Topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).

<div>

## <a name="to-define-a-front-end-pool"></a>Pour définir un pool frontal

1.  Dans l’Assistant Définir un nouveau pool frontal, sur la page **Définir le nouveau pool frontal**, cliquez sur **Suivant**.

2.  Dans la page définir le nom de domaine **complet du pool frontal** , entrez un nom de domaine complet (FQDN) pour le pool que vous créez, cliquez sur **pool de serveurs frontaux Enterprise Edition**, puis cliquez sur **suivant**.

3.  Sur la page **définir les ordinateurs de ce pool** , entrez le nom de domaine complet (FQDN) de l’ordinateur du premier serveur frontal dans le pool, puis cliquez sur **Ajouter**. Répétez cette étape pour tous les ordinateurs supplémentaires (jusqu’à douze) que vous souhaitez ajouter au pool, puis cliquez sur **suivant**.

4.  Dans la page **Sélectionner les fonctionnalités**, activez les cases à cocher correspondant aux fonctionnalités souhaitées pour ce pool frontal. Par exemple, si vous déployez uniquement les fonctionnalités de messagerie instantanée et de présence, vous devez activer la case à cocher **Conférence** pour autoriser la messagerie instantanée à plusieurs, mais ne pas sélectionner les cases à cocher Conférence rendez **-** vous, **voix entreprise**ou **contrôle d’admission des appels** , car elles représentent des fonctionnalités de conférence vocale, vidéo et de collaboration.
    
      - **Conférence**     Cette sélection active un ensemble complet de fonctionnalités, notamment :
        
          - la messagerie instantanée avec plus de deux utilisateurs dans le cadre d’une session de messagerie instantanée ;
        
          - la conférence qui inclut la collaboration sur des documents, le partage d’application et le partage du Bureau ;
        
          - Conférence a/V, qui permet aux utilisateurs d’effectuer des conférences audio/vidéo (A/V) en temps réel sans avoir besoin de recourir à des services externes, tels que le service Live Meeting ou un pont audio tiers.
    
      - Conférence rendez **-vous (PSTN)**     Permet aux utilisateurs de rejoindre la partie audio d’une conférence Lync Server 2013 à l’aide d’un téléphone RTC (réseau téléphonique commuté) sans avoir besoin d’un fournisseur de services d’audioconférence.
    
      - **Voix entreprise**     Voix entreprise est la solution voix sur IP (VoIP) dans Lync Server 2013 qui permet aux utilisateurs de passer et de recevoir des appels téléphoniques. Vous devez déployer cette fonctionnalité si vous envisagez d’utiliser Lync Server 2013 pour les appels vocaux, la messagerie vocale et d’autres fonctions qui utilisent un périphérique matériel ou un client logiciel.
    
      - **Contrôle d’admission des appels (CAC)**     Le contrôle d’admission des appels détermine, en fonction de la bande passante réseau disponible, si des sessions de communication en temps réel telles que des appels vocaux ou vidéo doivent être établies ou non. Si vous avez uniquement déployé les fonctionnalités de messagerie instantanée et de présence, CAC n’est pas nécessaire car aucune de ces deux fonctionnalités n’utilise CAC.
    
      - **Archivage**     L’archivage vous permet d’archiver le contenu de messagerie instantanée, le contenu de conférence (réunion), ou les deux, qui sont envoyés par le biais de Lync Server 2013.
    
      - **Surveillance**     Le serveur de surveillance vous permet de collecter des données numériques qui décrivent la qualité des médias sur votre réseau et les points de terminaison, les informations d’utilisation relatives aux appels VoIP, les messages de messagerie instantanée, les conversations A/V, les réunions, le partage d’application et les transferts de fichiers, ainsi que les informations d’erreur et de dépannage pour les appels ayant échoué.
    
    <div>
    

    > [!NOTE]
    > Si vous souhaitez activer le contrôle d’admission des appels dans votre déploiement, il vous faut activer cette fonctionnalité dans un pool par site central. Le contrôle d’admission des appels est recommandé lorsque vous déployez les fonctionnalités vocales ou la conférence A/V.

    
    </div>
    
    Le tableau suivant indique les fonctionnalités disponibles (en haut) et les fonctions proposées aux utilisateurs (à gauche). Sélectionnez les différents choix dans le tableau pour activer ces fonctionnalités dans votre organisation.
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th>Conférence</th>
    <th>Conférence rendez-vous</th>
    <th>Voix Entreprise</th>
    <th>Contrôle d’admission des appels</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Messagerie instantanée et présence</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p>Conférence</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p>Conférence A/V</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td><p>X</p></td>
    </tr>
    <tr class="even">
    <td><p>Voix Entreprise</p></td>
    <td></td>
    <td></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    </tr>
    </tbody>
    </table>


5.  Sur la page **Sélectionner des rôles serveur colocalisés** , vous pouvez colocaliser le serveur de médiation sur le serveur frontal ou le déployer en tant que serveur autonome.
    
    Vous pouvez colocaliser le serveur de médiation sur le pool frontal.
    
      - Si vous avez l’intention d’colocaliser le serveur de médiation sur le pool frontal Enterprise Edition, vérifiez que la case à cocher est activée. Les rôles serveur seront déployés sur les serveurs du pool.
    
      - Si vous avez l’intention de déployer le serveur de médiation en tant que serveur autonome, désactivez la case à cocher appropriée. Vous allez déployer le serveur de médiation dans une étape de déploiement distincte après avoir déployé entièrement le serveur frontal.
    
    <div>
    

    > [!NOTE]
    > Nous vous recommandons de colocaliser le serveur de médiation si cela vous est possible. Pour plus d’informations sur la prise en charge des serveurs de médiation colocalisés ou autonomes, voir <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">composants et topologies pour le serveur de médiation dans Lync server 2013</A> dans la documentation de planification.

    
    </div>

6.  La page **rôles serveur associés à ce pool frontal** vous permet de définir et d’associer des rôles serveur au pool frontal. Le rôle suivant est disponible :
    
    **Activer un pool**     de serveurs Edge Définit et associe un serveur Edge unique ou un pool de serveurs Edge. Un serveur Edge facilite la communication et la collaboration entre les utilisateurs au sein de l’organisation et les personnes extérieures à l’organisation, y compris les utilisateurs fédérés.
    
    Vous disposez de deux scénarios pour déployer et associer des rôles serveur :
    
    Dans le premier scénario, vous définissez une nouvelle topologie pour un nouvelle installation. Vous pouvez procéder à l’installation de deux façons différentes :
    
      - Laissez la case à cocher désactivée et définissez la topologie. Une fois que vous avez publié, configuré et testé les rôles serveur frontal et principal, vous pouvez réexécuter le générateur de topologie pour ajouter les serveurs de rôle à la topologie. Cette stratégie vous permettra de tester le pool frontal et le serveur exécutant SQL Server sans complications supplémentaires de rôles supplémentaires. Une fois que vous avez terminé les tests initiaux, vous pouvez réexécuter le générateur de topologie pour sélectionner les rôles à déployer.
    
      - Sélectionnez les rôles à installer, puis configurez le matériel en fonction des rôles sélectionnés.
    
    Pour le scénario 2, vous disposez d’un déploiement existant et votre infrastructure est prête pour de nouveaux rôles, ou vous devez associer des rôles existants à un nouveau serveur frontal :
    
      - Dans ce cas, vous allez sélectionner les rôles que vous envisagez de déployer ou d’associer au nouveau serveur frontal. Dans les deux cas, vous devez définir les rôles, configurer le matériel nécessaire et effectuer l’installation.

7.  Dans la page **Définir le magasin SQL**, effectuez l’une des opérations suivantes :
    
      - Pour utiliser un magasin SQL Server qui a déjà été défini dans votre topologie, sélectionnez une instance dans **Magasin SQL**.
    
      - Pour définir une nouvelle instance SQL Server pour stocker les informations du pool, cliquez sur **nouveau** , puis spécifiez le **nom de domaine complet SQL Server**dans la boîte de dialogue **définir un nouveau magasin SQL** .
    
      - Pour spécifier le nom d’une instance SQL Server, sélectionnez **Instance nommée**, puis spécifiez le nom de l’instance.
    
      - Pour utiliser l’instance par défaut, cliquez sur **Instance par défaut**.
    
      - Pour utiliser la mise en miroir SQL, sélectionnez **Activer la mise en miroir SQL** et sélectionnez une instance existante ou créez-en une nouvelle.

8.  Dans la page **Définir le partage de fichiers**, effectuez l’une des opérations suivantes :
    
      - Pour utiliser un partage de fichiers qui a déjà été défini dans votre topologie, sélectionnez **Utiliser un partage de fichiers précédemment défini**.
    
      - Pour définir un nouveau partage de fichiers, sélectionnez **Définir un nouveau partage de fichiers**. Dans la zone **Nom de domaine complet du serveur de fichiers**, entrez le nom de domaine complet (FQDN) du serveur de fichiers existant où le partage de fichiers doit être placé, puis entrez un nom pour le partage de fichiers dans la zone **Partage de fichiers**.
    
    <div>
    

    > [!IMPORTANT]
    > Le partage de fichiers pour Lync Server 2013 ne peut pas se trouver sur le serveur frontal. Notez que dans cet exemple, le partage de fichiers se situait sur le serveur principal SQL Server. Il ne s’agit peut-être pas d’un emplacement optimal pour les besoins de votre organisation ; un serveur de fichiers peut s’avérer être un meilleur choix. Vous pouvez définir le partage de fichiers sans qu’il soit nécessaire de le créer. Vous devrez créer le partage de fichiers à l’emplacement que vous définissez avant de publier la topologie.

    
    </div>

9.  Dans la page **Spécifier l’URL des services web**, effectuez l’une ou plusieurs des opérations suivantes :
    
    <div>
    

    > [!IMPORTANT]
    > L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est https://pool01.contoso.net , l’URL de base est pool01.contoso.net.

    
    </div>
    
    <div>
    

    > [!WARNING]
    > Si vous avez plusieurs pools frontaux ou serveurs frontaux, le nom de domaine complet des services Web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que <STRONG>pool01.contoso.com</STRONG>, vous ne pouvez pas utiliser <STRONG>pool01.contoso.com</STRONG> pour un autre pool frontal ou serveur frontal.

    
    </div>
    
    1.  Si vous configurez l’équilibrage de la charge DNS, activez la case à cocher **remplacer le nom de domaine complet du pool des services Web internes** , entrez l’URL de base interne (qui doit être différente du nom de domaine complet du pool et peut être, par exemple, Internal \<your base URL\> ) dans **URL de base interne**.
        
        <div>
        

        > [!WARNING]
        > Si vous décidez de remplacer les services Web internes par un nom de domaine complet indépendant, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool directeur. <STRONG>Utilisez uniquement des caractères standard</STRONG> (tels que a – z, a – z, 0 – 9 et des traits d’Union) lors de la définition des URL ou des noms de domaine complets. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard d’une URL ou d’un nom de domaine complet ne sont souvent pas pris en charge par le DNS externe et les autorités de certification publiques (c’est-à-dire, lorsque l’URL ou le nom de domaine complet doivent être attribués au nom de sujet ou à l’autre nom de l’objet dans le certificat).

        
        </div>
    
    2.  Entrez l’URL de base externe dans **URL de base externe** (facultatif). Entrez l’URL de base externe pour la différencier de votre nom de domaine interne. Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com. Définissez alors l’URL à l’aide du nom de domaine contoso.com. Ceci est également important dans le cas d’un proxy inverse. Le nom de domaine de l’URL de base externe est le même que le nom de domaine du nom de domaine complet du proxy inverse. La messagerie instantanée et la présence nécessitent un accès HTTP au pool frontal.
    
    <div>
    

    > [!NOTE]
    > Pour utiliser l’équilibrage de charge DNS, vous devez créer les enregistrements DNS appropriés. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-configure-dns-for-load-balancing.md">configurer DNS pour l’équilibrage de charge dans Lync Server 2013</A>.

    
    </div>

10. Si vous avez sélectionné **Conférence** dans la page **Sélectionner des fonctionnalités** , dans la page **Sélectionner un serveur Office Web Apps Server** , sélectionnez **associer un pool à un serveur Office Web Apps Server** , puis cliquez sur **nouveau** (ou sélectionnez un serveur Office Web Apps existant dans la liste déroulante).

11. Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps**, tapez le nom de domaine complet de votre ordinateur Office Web Apps Server dans la zone **Nom de domaine complet du serveur Office Web Apps**. L’URL de découverte du serveur Office Web Apps Server est alors automatiquement entrée dans la zone **URL de découverte du serveur Office Web Apps**.
    
    Si Office Web Apps Server est installé sur site et dans la même zone de réseau que Lync Server 2013, l’option le **serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)** ne doit pas être sélectionné.
    
    Si le serveur Office Web Apps Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez alors l’option **Le serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)**.
    
    <div>
    

    > [!NOTE]
    > Pour plus d’informations, reportez-vous à la rubrique Configuration de l' <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">intégration avec Office Web Apps Server et Lync Server 2013</A>.

    
    </div>

12. Dans la page **Définir le magasin SQL Server d’archivage**, sélectionnez une instance existante ou SQL Server, ou définissez une nouvelle instance pour stocker les données associées aux données d’archivage.

13. Dans la page **Définir le magasin SQL Server pour la surveillance**, sélectionnez une instance existante ou SQL Server, ou définissez une nouvelle instance pour stocker les données associées aux données de surveillance.

14. Cliquez sur **Suivant**. Si vous avez défini d’autres serveurs de rôle sur la page **rôles serveur associés avec ce pool frontal** , des pages d’Assistant Configuration de rôle distinctes s’ouvrent pour vous permettre de configurer les rôles serveur. Pour plus d’informations, voir :
    
    [Déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md)

15. Si vous n’avez pas sélectionné de rôles serveur supplémentaires à configurer et à déployer, ou si vous avez terminé la configuration de rôles serveur supplémentaires, cliquez sur **Terminer**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

