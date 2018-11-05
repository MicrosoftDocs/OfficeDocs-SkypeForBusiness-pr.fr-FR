---
title: "Lync Server 2013 : Déf. et conf. pool frontal ou serv. Standard Edition"
TOCTitle: Définition et configuration d’un pool frontal ou d’un serveur Standard Edition
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398538(v=OCS.15)
ms:contentKeyID: 49297670
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition et configuration d’un pool frontal ou d’un serveur Standard Edition dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Pour effectuer cette procédure, il n’est pas nécessaire d’appartenir à un groupe d’administrateurs local ou de domaines privilégiés. Vous devez simplement ouvrir une session sur un ordinateur en tant qu’utilisateur standard.

Si vous déployez un serveur Enterprise, un nombre minimal de serveurs frontaux doivent s’exécuter en continu dans un pool. Le tableau ci-dessous résume ces exigences :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre total de serveurs frontaux dans le pool</th>
<th>Nombre de serveurs devant être exécutés pour que le pool soit opérationnel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1-2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>7-8</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>9-10</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>11-12</p></td>
<td><p>6</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Pour Lync Server 2013, lorsque vous ajoutez ou supprimez un serveur frontal du pool, vous devez redémarrer les services. La suppression et l’ajout de serveurs doivent être effectuées séparément. Par exemple, si vous allez ajouter deux serveurs frontaux et en supprimer deux autres, procédez comme suit :<ol><li><p>Supprimez les deux serveurs frontaux.</p></li><li><p>Publiez et réactivez la topologie.</p></li>
> <li><p>Redémarrez les services.</p></li>
> <li><p>Ajoutez les deux serveurs frontaux.</p></li>
> <li><p>Publiez et réactivez la topologie.</p></li>
> <li><p>Redémarrez les services.</p></li></ol>


Après avoir défini votre topologie, procédez comme suit pour définir un pool de serveurs frontaux pour votre site. Pour plus d’informations sur la définition de la topologie, reportez-vous à [Définition et configuration d’une topologie dans le générateur de topologie pour Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).

## Pour définir un pool de serveurs frontaux

1.  Dans l’Assistant Définir un nouveau pool frontal, dans la page **Définir le nouveau pool de serveurs frontaux**, cliquez sur **Suivant** .

2.  Dans la page **Définir le FQDN du pool de serveurs frontaux**, saisissez le nom de domaine complet (FQDN) du pool que vous créez, cliquez sur **pool de serveurs frontaux Enterprise Edition**, puis sur **Suivant**.

3.  Dans la page **Définissez les ordinateurs inclus dans ce pool**, entrez le FQDN d’un ordinateur pour le premier serveur frontal dans le pool, puis cliquez sur **Ajouter**. Répétez cette étape pour les autres ordinateurs (jusqu’à douze) à ajouter au pool, puis sur **Suivant**.

4. Dans la page **Sélectionner les fonctionnalités**, activez les cases à cocher correspondant aux fonctionnalités souhaitées pour ce pool frontal. Par exemple, si vous déployez uniquement les fonctionnalités de messagerie instantanée et de présence, activez la case **Conférence** pour autoriser la messagerie instantanée à plusieurs, mais n’activez pas les cases à cocher **Conférence rendez-vous (RTC)**, **Voix Entreprise** ou **Contrôle d’admission d’appel**, car elles représentent les fonctionnalités de voix, de vidéo et de conférence collaborative.
    
      - **Conférence** Cette sélection permet d’accéder à un ensemble complet de fonctionnalités, dont :
        
          - la messagerie instantanée avec plus de deux utilisateurs dans le cadre d’une session de messagerie instantanée ;
        
          - la conférence qui inclut la collaboration sur des documents, le partage d’application et le partage du Bureau ;
        
          - la conférence A/V qui permet aux utilisateurs d’effectuer des conférences audio/vidéo (A/V) en temps réel sans devoir recourir à des services externes, tels que le service Live Meeting ou un pont audio tiers.
    
      - **Conférence rendez-vous (RTC)** Permet aux utilisateurs de prendre part à la partie audio d’une conférence Lync Server 2013 via un téléphone RTC sans avoir besoin de recourir à un fournisseur de services d’audioconférence.
    
      - **Voix Entreprise** Voix Entreprise est la solution voix sur IP (VoIP) de Lync Server 2013 qui permet aux utilisateurs de passer et de recevoir des appels téléphoniques. Déployez cette fonctionnalité si vous prévoyez d’utiliser Lync Server 2013 pour les appels vocaux, la messagerie vocale et d’autres fonctions qui utilisent un périphérique matériel ou un client logiciel.
    
      - **Contrôle d’admission des appels (CAC)** CAC détermine, en fonction de la bande passante réseau disponible, si des sessions de communication en temps réel, telles que des appels vocaux ou vidéo, peuvent être établies. Si vous avez uniquement déployé les fonctionnalités de messagerie instantanée et de présence, CAC n’est pas nécessaire car aucune de ces deux fonctionnalités n’utilise CAC.
    
      - **Archivage**   L’archivage vous offre un moyen d’archiver le contenu de messagerie instantanée, le contenu de conférence (réunion) ou les deux, envoyés via Lync Server 2013.
    
      - **Surveillance**   Le serveur de surveillance vous permet de collecter des données numériques qui décrivent la qualité des médias de votre réseau et vos points de terminaison, des informations d’utilisation liées aux appels VoIP, messages de messagerie instantanée, conversations A/V, réunions, partage d’application et transferts de fichiers, ainsi que des informations sur les erreurs des appels et des informations d’identification et de résolution des problèmes des appels qui ont échoué.
    
    > [!NOTE]  
    > Si vous souhaitez activer le contrôle d’admission des appels dans votre déploiement, il vous faut activer cette fonctionnalité dans un pool par site central. Le contrôle d’admission des appels est recommandé lorsque vous déployez les fonctionnalités vocales ou la conférence A/V.    
    
    
    Le tableau ci-dessous indique les fonctionnalités disponibles (en haut) et les fonctions proposées aux utilisateurs (à gauche). Sélectionnez les différents choix dans le tableau pour activer ces fonctionnalités dans votre organisation.
    
    
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
    <td><p></p></td>
    <td><p></p></td>
    <td><p></p></td>
    </tr>
    <tr class="even">
    <td><p>Conférence</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td><p></p></td>
    <td><p></p></td>
    </tr>
    <tr class="odd">
    <td><p>Conférence A/V</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td><p></p></td>
    <td><p>X</p></td>
    </tr>
    <tr class="even">
    <td><p>Voix Entreprise</p></td>
    <td><p></p></td>
    <td><p></p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    </tr>
    </tbody>
    </table>


5.  Dans la page **Sélectionner des rôles serveur colocalisés** , vous pouvez colocaliser le serveur de médiation sur le serveur frontal, ou le déployer en tant que serveur autonome.
    
    Vous pouvez colocaliser le serveur de médiation sur le pool de serveurs frontaux.
    
      - Si vous prévoyez de colocaliser le serveur de médiation sur le pool de serveurs frontaux Enterprise Edition, vérifiez que les cases à cocher sont activées. Les rôles serveur seront déployés sur les serveurs du pool.
    
      - Si vous prévoyez de déployer le serveur de médiation en tant que serveur autonome, désactivez la case à cocher appropriée. Vous déploierez le serveur de médiation dans une étape de déploiement distincte une fois le serveur frontal entièrement déployé.
    
    > [!NOTE]  
    > Nous vous recommandons de colocaliser le serveur de médiation si cela vous est possible. Pour plus d’informations sur la prise en charge des serveurs de médiation colocalisés ou autonomes, reportez-vous à <a href="lync-server-2013-components-and-topologies-for-mediation-server.md">Composants et topologies utilisés pour le serveur de médiation dans Lync Server 2013</a> dans la documentation de planification.

6.  La page **Rôles serveur associés à ce pool frontal** vous permet de définir et d’associer des rôles serveur au pool de serveurs frontaux. Le rôle suivant est disponible :
    
    **Activer un pool de serveurs Edge** Définit et associe un serveur Edge unique ou un pool de serveurs Edge. Un serveur Edge facilite la communication et la collaboration entre les utilisateurs au sein de l’organisation et les personnes qui travaillent en dehors de celle-ci, notamment les utilisateurs fédérés.
    
    Vous disposez de deux scénarios pour déployer et associer des rôles serveur :
    
    Dans le premier scénario, vous définissez une nouvelle topologie pour un nouvelle installation. Vous pouvez procéder à l’installation de deux façons différentes :
    
      - Laissez la case à cocher désactivée et définissez la topologie. Une fois les rôles serveur frontal et principal publiés, configurés et testés, vous pouvez réexécuter Générateur de topologie afin de les ajouter à la topologie. Cette stratégie vous permettra de tester le pool de serveurs frontaux et le serveur exécutant SQL Server sans les autres complications d’autres rôles. Une fois les tests initiaux réalisés, vous pouvez réexécuter Générateur de topologie afin de sélectionner les rôles à déployer.
    
      - Sélectionnez les rôles à installer, puis configurez le matériel en fonction des rôles sélectionnés.
    
    Dans le deuxième scénario, vous disposez déjà d’un déploiement et votre infrastructure est prête pour de nouveaux rôles, ou vous devez associer des rôles existants à un nouveau serveur frontal :
    
      - Dans ce cas, sélectionnez les rôles que vous souhaitez déployer ou associer avec le nouveau serveur frontal. Dans les deux cas, vous devez définir les rôles, configurer le matériel nécessaire et effectuer l’installation.

7.  Dans la page **Définir le magasin SQL** , effectuez l’une des opérations suivantes :
    
      - Pour utiliser un magasin SQL Server qui a déjà été défini dans votre topologie, sélectionnez une instance dans **Magasin SQL** .
    
      - Pour définir une nouvelle instance SQL Server pour stocker les informations du pool, cliquez sur **Nouveau** , puis spécifiez le **Nom de domaine complet du serveur SQL Server** dans la boîte de dialogue **Définir un nouveau magasin SQL** .
    
      - Pour spécifier le nom d’une instance SQL Server, sélectionnez **Instance nommée** , puis spécifiez le nom de l’instance.
    
      - Pour utiliser l’instance par défaut, cliquez sur **Instance par défaut** .
    
      - Pour utiliser la mise en miroir SQL, sélectionnez **Activer la mise en miroir SQL** et sélectionnez une instance existante ou créez-en une nouvelle.

8.  Dans la page **Définir le partage de fichiers** , effectuez l’une des opérations suivantes :
    
      - Pour utiliser un partage de fichiers qui a déjà été défini dans votre topologie, sélectionnez **Utiliser un partage de fichiers précédemment défini** .
    
      - Pour définir un nouveau partage de fichiers, sélectionnez **Définir un nouveau partage de fichiers** . Dans la zone **Nom de domaine complet du serveur de fichiers** , entrez le nom de domaine complet (FQDN) du serveur de fichiers existant où le partage de fichiers doit être placé, puis entrez un nom pour le partage de fichiers dans la zone **Partage de fichiers** .
    
    > [!IMPORTANT]  
    > Le partage de fichiers de Lync Server 2013 ne peut se trouver sur le serveur frontal. Notez que dans cet exemple, le partage de fichiers se situait sur le serveur principal SQL Server. Il ne s’agit peut-être pas d’un emplacement optimal pour les besoins de votre organisation ; un serveur de fichiers peut s’avérer être un meilleur choix. Vous pouvez définir le partage de fichiers sans qu’il soit nécessaire de le créer. Vous devrez créer le partage de fichiers à l’emplacement que vous définissez avant de publier la topologie.

9.  Dans la page **Spécifier l’URL des services web** , effectuez l’une ou plusieurs des opérations suivantes :
    
    > [!IMPORTANT]  
    > L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.    
    > [!WARNING]  
    > Si vous disposez de plus d’un pool de serveurs frontaux ou serveur frontal, le nom de domaine complet des services web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services web externes d’un serveur frontal en tant que <strong>pool01.contoso.com</strong>, vous ne pouvez pas utiliser <strong>pool01.contoso.com</strong> pour un autre pool de serveurs frontaux ou serveur frontal.    
    1.  Si vous configurez l’équilibrage de la charge DNS, activez la case à cocher **Remplacer le nom de domaine complet du pool des services web internes** , entrez l’URL de base interne (qui doit être différente du nom de domaine complet du pool, par exemple, \<votre URL de base\> interne) dans **URL de base interne** .
        
        > [!WARNING]  
        > Si vous choisissez de remplacer le nom des services web internes par un nom de domaine complet personnalisé, chaque nom de domaine complet doit être différent des autres noms de pool de serveurs frontaux, directeur ou pool de directeurs. <strong>Utilisez uniquement des caractères standard</strong> (A–Z, a–z, 0–9 et tirets) lorsque vous définissez des URL ou des noms de domaine complets. N’utilisez ni caractère Unicode ni trait de soulignement. En général, les DNS externes et les autorités de certification publiques ne prennent pas en charge les caractères non standard dans les URL ou noms de domaine complets (c’est-à-dire lorsque l’URL ou le nom de domaine complet doit être affecté au nom d’objet ou autre nom d’objet du certificat).    
    2.  Entrez l’URL de base externe dans **URL de base externe** (facultatif). Entrez l’URL de base externe pour la différencier de votre nom de domaine interne. Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com. Définissez alors l’URL à l’aide du nom de domaine contoso.com. Cela est également important dans le cas d’un proxy inverse. Le nom de domaine de l’URL de base externe est le même que le nom de domaine du nom de domaine complet du proxy inverse. Les fonctionnalités de messagerie instantanée et de présence ne nécessitent pas d’accès HTTP au pool de serveurs frontaux.
    
    > [!NOTE]  
    > Pour utiliser l’équilibrage de charge DNS, vous devez créer les enregistrements DNS appropriés. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configure-dns-for-load-balancing.md">Configuration du DNS pour l’équilibrage de charge dans Lync Server 2013</a>.

10. Si vous avez sélectionné **Conférence** dans la page **Sélectionner les fonctionnalités** , dans la page **Sélectionner un serveur Office Web Apps** , sélectionnez **Associer un pool avec un serveur Office Web Apps** , puis cliquez sur **Nouveau** (ou sélectionnez un serveur Office Web Apps Server existant dans la liste déroulante).

11. Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps** , tapez le nom de domaine complet (FQDN) de votre ordinateur Office Web Apps Server dans la zone **Nom de domaine complet (FQDN) du serveur Office Web Apps**  ; à ce moment-là, l’URL de découverte de votre serveur Office Web Apps Server doit s’afficher automatiquement dans la zone **URL de découverte du serveur Office Web Apps** .
    
    Si le serveur Office Web Apps Server est installé localement et dans la même zone de réseau que Lync Server 2013, alors il est préférable de ne pas sélectionner l’option **Le serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)** .
    
    Si le serveur Office Web Apps Server est déployé en dehors de votre pare-feu interne, alors sélectionnez l’option **Le serveur Office Web Apps est déployé sur un réseau \_externe (périmètre/Internet)** .
    
    > [!NOTE]  
    > Pour plus d’informations, reportez-vous à la section <a href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuration de l’intégration à Office Web Apps Server et Lync Server 2013</a>.

12. Dans la page **Définir le magasin SQL Server d’archivage** , sélectionnez une instance existante ou SQL Server, ou définissez une nouvelle instance pour stocker les données associées aux données d’archivage.

13. Dans la page **Définir le magasin SQL Server pour la surveillance** , sélectionnez une instance existante ou SQL Server, ou définissez une nouvelle instance pour stocker les données associées aux données de surveillance.

14. Cliquez sur **Suivant** . Si vous avez défini d’autres rôles serveur sur la page **Rôles serveur associés à ce pool frontal**, différentes pages de l’assistant de configuration de rôle s’ouvriront afin que vous puissiez configurer les rôles serveur. Pour plus d’informations, reportez-vous à :
    
    [Déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md)

15. Si vous n’avez pas sélectionné de rôles serveur supplémentaires à configurer et à déployer, ou si vous avez terminé la configuration de rôles serveur supplémentaires, cliquez sur **Terminer** .

