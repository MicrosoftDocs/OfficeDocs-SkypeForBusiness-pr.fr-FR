---
title: Créer et publier une nouvelle topologie dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 451c41a1-b8c5-4dc3-9e48-0da9ed5381a1
description: 'Résumé : Découvrez comment créer, publier et vérifier une nouvelle topologie avant d’installer Skype entreprise Server. Télécharger une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft pour :.'
ms.openlocfilehash: 631b0e44dfc632cbcc07f4fa6020e39b8dd292e0
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791802"
---
# <a name="create-and-publish-new-topology-in-skype-for-business-server"></a>Créer et publier une nouvelle topologie dans Skype entreprise Server
 
**Résumé :** Découvrez comment créer, publier et vérifier une nouvelle topologie avant d’installer Skype entreprise Server. Télécharger une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Microsoft pour :.
  
Pour pouvoir installer le système Skype entreprise Server sur chacun des serveurs de la topologie, vous devez créer une topologie et la publier. Lorsque vous publiez une topologie, vous chargez les informations dans la base de données du magasin central de gestion. S’il s’agit d’un pool Enterprise Edition, vous créez la base de données du magasin central de gestion la première fois que vous publiez une nouvelle topologie. S’il s’agit de Standard Edition, vous devrez exécuter le processus Préparer d’abord le serveur Standard Edition Server depuis l’assistant Déploiement avant de publier une topologie. Il prépare l’installation de Standard Edition en installant une instance de SQL Server Express Edition et en créant le magasin central de gestion. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Cependant, vous devez suivre les étapes 6,7 et 8 dans l’ordre et après avoir effectué les étapes 1 à 5, comme expliqué dans le diagramme. L’étape 6 sur 8 vous expliquera comment créer et publier une nouvelle topologie.
  
![Schéma de vue d’ensemble](../../media/c5c09ba2-c98b-4194-9857-7c3087c5560e.png)
  
## <a name="create-and-publish-new-topology"></a>Créer et publier une nouvelle topologie

Vous pouvez utiliser le générateur de topologie Skype entreprise Server pour concevoir, définir, configurer et publier des topologies. Cet outil a été installé lorsque vous avez précédemment installé les Outils d’administration, comme expliqué auparavant dans l’article. Il existe de nombreux choix différents lorsque vous créez une topologie. Au cours de cette procédure, vous allez créer une topologie de base avec conférence.
  
> [!IMPORTANT]
> Pour pouvoir fonctionner, Skype entreprise Server nécessite SQL Server. Les bases de données primaires sont qualifiées de magasin central de gestion. Si vous déployez Enterprise Edition, ces bases de données sont créées lorsque vous publiez la topologie (en suivant les étapes mentionnées plus haut). Dans ce cas, le Générateur de topologies vous demandera les informations de connexion pour une installation de SQL Server. Si vous souhaitez déployer Standard Edition, vous devez installer SQL Server Express Edition avant de définir et publier la nouvelle topologie. Pour installer SQL Server Express Edition, ouvrez l’assistant Déploiement sur le serveur qui servira de serveur frontal, puis exécutez Préparer d’abord le serveur Standard Edition Server. Lorsque vous cliquez sur Préparer d’abord le serveur Standard Edition Server, l’assistant Déploiement installe automatiquement SQL Server Express Edition et crée les bases de données du magasin central de gestion. 
  
### <a name="create-a-new-topology"></a>Créer une nouvelle topologie

1. Connectez-vous en tant qu’utilisateur standard avec accès au Générateur de topologies.
    
2. Ouvrez le générateur de topologie Skype entreprise Server.
    
3. Sélectionnez **Nouvelle Topologie**, puis cliquez sur **OK**.
    
4. Sélectionnez un emplacement et un nom de fichier pour le fichier de configuration de topologie.
    
    > [!NOTE]
    > La configuration de topologie est sauvegardée en tant que fichier Topology Builder XML (.tbxml). Lorsque vous publiez une topologie, vous envoyez les informations de configuration du fichier à la base de données SQL Server. À l’avenir, lorsque vous ouvrirez le Générateur de topologies, vous pourrez directement télécharger la configuration existante à du serveur SQL Server au Générateur de topologies, et la republier vers le serveur SQL Server ou la sauvegarder en tant que fichier de configuration Topology Builder. 
  
5. Dans **Définir le domaine principal**, entrez le **Domaine SIP principal**, puis cliquez sur **Suivant**. Dans cet exemple, nous utilisons **contoso.local**, comme mentionné dans le schéma.
    
     ![Définissez le domaine SIP principal.](../../media/353e6b38-485f-4042-8585-aefa6c74b554.png)
  
6. Ajoutez éventuellement d’autres domaines SIP pris en charge, puis cliquez sur **Suivant**.
    
7. Entrez un **Nom** et une **Description** pour le premier site (emplacement), puis cliquez sur **Suivant**, comme mentionné dans le schéma.
    
     ![Définissez le premier site (emplacement).](../../media/d8b6c54a-2011-4efb-97fb-a4de0f11303c.png)
  
8. Entrez la **Ville**, le **Département/la province**, et le **Code de pays/région** du site, puis cliquez sur **Suivant**.
    
9. Cliquez sur **Terminer** pour terminer le processus de définition d’une nouvelle topologie. L’assistant Nouveau serveur frontal se lancera automatiquement.
    
### <a name="define-a-front-end-pool-or-standard-edition-server"></a>Définition d’un pool frontal ou d’un serveur Standard Edition

1. Relisez les conditions préalables de l’assistant, puis cliquez sur **Suivant**.
    
2. Entrez le nom de domaine complet (FQDN) du pool, sélectionnez **Pool frontal Enterprise Edition** ou **Serveur Standard Edition**, puis cliquez sur **Suivant**, comme mentionné dans le schéma.
    
    > [!TIP]
    > Skype entreprise Server Enterprise Edition peut inclure plusieurs serveurs travaillant ensemble pour fournir le rôle frontal. Lorsque plusieurs serveurs sont utilisés à cette fin, ils sont qualifiés de pool. Par conséquent, l’ensemble des serveurs qui fonctionnent ensemble en tant que serveur frontal est également appelé pool frontal. Skype entreprise Server Standard Edition ne peut inclure qu’un seul serveur pour fournir le rôle frontal. Il est communément appelé pool frontal même si un seul serveur joue ce rôle. 
  
     ![Définissez le pool frontal.](../../media/c1447557-261e-4260-a362-ab8d19070eb9.png)
  
3. Entrez le nom de domaine complet (FQDN) de tous les ordinateurs dans le pool, puis cliquez sur **Suivant**, comme mentionné dans le schéma.
    
     ![Définissez les ordinateurs du pool.](../../media/1106b4f3-8745-485b-b495-f885a5dfefda.png)
  
4. Sélectionnez les fonctionnalités qui seront incluses dans la topologie, puis cliquez sur **Suivant**, comme mentionné dans le schéma.
    
    > [!NOTE]
    > Skype entreprise Server inclut de nombreuses fonctionnalités avancées. Relisez la documentation de déploiement et de planification pour chaque fonctionnalité que vous souhaitez utiliser. 
  
     ![Sélectionnez des fonctionnalités pour le déploiement.](../../media/77257588-d0e1-4517-a12a-869ffe009353.png)
  
5. Dans la page **Sélectionner des rôles de serveurs colocalisés** , vous pouvez choisir de collocate le serveur de médiation sur le serveur frontal, ou vous pouvez choisir de le déployer en tant que serveur autonome.
    
    Si vous souhaitez colocaliser le serveur de médiation sur le pool frontal Enterprise Edition, assurez-vous que la case est cochée. Le rôle serveur sera déployé sur les serveurs du pool. Si vous souhaitez déployer le serveur de médiation en tant que serveur autonome, désactivez la case à cocher. Vous déploierez le serveur de médiation dans une étape de déploiement séparée après le déploiement complet du serveur frontal. Pour plus d’informations sur la gestion de la colocalisation, voir [notions de base de la topologie pour Skype entreprise Server](../../plan-your-deployment/topology-basics/topology-basics.md).
    
6. La page **Rôles serveur associés à ce pool frontal** vous permet de définir et d’associer des rôles serveur au pool frontal. Le rôle suivant est disponible :
    
    **Activer un pool de bords** Définit et associe un serveur Edge unique ou un pool de serveurs Edge. Un serveur Edge facilite la communication et la collaboration entre les utilisateurs au sein de l’organisation et les personnes qui travaillent en dehors de celle-ci, notamment les utilisateurs fédérés.
    
    Deux scénarios permettent de déployer et d’associer des rôles serveur :
    
    Dans le premier scénario, vous définissez une nouvelle topologie pour une nouvelle installation. Vous pouvez procéder à l’installation de l’une des deux façons suivantes :
    
   - Laissez la case à cocher désactivée et définissez la topologie. Une fois les rôles serveur frontal et principal publiés, configurés et testés, vous pouvez réexécuter le Générateur de topologies afin de les ajouter à la topologie. Cette stratégie vous permettra de tester le pool frontal et le serveur exécutant SQL Server sans les autres complications d’autres rôles. Une fois les tests initiaux réalisés, vous pouvez réexécuter le Générateur de topologies afin de sélectionner les rôles à déployer.
    
   - Sélectionnez les rôles à installer, puis configurez le matériel en fonction des rôles sélectionnés.
    
     Dans le deuxième scénario, vous disposez déjà d’un déploiement et votre infrastructure est prête pour de nouveaux rôles, ou vous devez associer des rôles existants à un nouveau serveur frontal.
    
   - Dans ce cas, sélectionnez les rôles que vous souhaitez déployer ou associer avec le nouveau serveur frontal. Dans les deux cas, vous devez définir les rôles, configurer le matériel nécessaire et effectuer l’installation.
    
7. Ensuite, vous devrez définir le magasin SQL Server qui sera utilisé avec la topologie. Dans cet exemple, nous utilisons l’instance par défaut. Pour plus d’informations sur les fonctionnalités de SQL Server, comme la haute disponibilité, voir [prévoir une disponibilité élevée et une reprise après sinistre dans Skype entreprise Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
    
   - Pour utiliser un magasin SQL Server qui a déjà été défini dans votre topologie, sélectionnez une instance dans **Magasin SQL**.
    
   - Pour définir une nouvelle instance SQL Server pour stocker des informations de pool, cliquez sur **nouveau**, puis spécifiez le **nom de domaine complet SQL Server** dans la boîte de dialogue **définir un nouveau SQL Store** .
    
   - Pour spécifier le nom d’une instance SQL Server, sélectionnez **Instance nommée**, puis spécifiez le nom de l’instance.
    
   - Pour utiliser l’instance par défaut, cliquez sur **Instance par défaut**.
    
   - Pour utiliser la mise en miroir SQL, sélectionnez **Activer la mise en miroir SQL** et sélectionnez une instance existante ou créez-en une nouvelle.

     > [!NOTE]
     > La mise en miroir SQL est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. Les groupes de disponibilité AlwaysOn, les instances de clusters de basculement AlwaysOn (ICF) et les méthodes de regroupement de relais SQL sont préférés dans Skype entreprise Server 2019.
    
     Pour cet exemple, entrez **Nom de domaine complet de SQL Server**, configurez les paramètres de haute disponibilité, puis cliquez sur **OK**, comme mentionné dans le schéma.
    
     ![Créez un magasin SQL Server.](../../media/12822cf9-8608-43c0-94ce-2ca8b3a0ffd5.png)
  
8. Décidez si vous souhaitez activer la mise en miroir du magasin SQL Server ou le témoin de mise en miroir SQL Server, puis cliquez sur **Suivant**.
    
9. Définissez le partage de fichiers que vous souhaitez utiliser.
    
   - Pour utiliser un partage de fichiers qui a déjà été défini dans votre topologie, sélectionnez **Utiliser un partage de fichiers précédemment défini**.
    
   - Pour définir un nouveau partage de fichiers, sélectionnez **Définir un nouveau partage de fichiers**. Dans la zone **Nom de domaine complet du serveur de fichiers**, entrez le nom de domaine complet (FQDN) du serveur de fichiers existant où le partage de fichiers doit être placé, puis entrez un nom pour le partage de fichiers dans la zone **Partage de fichiers**.
    
     Pour cet exemple, cliquez sur **Définir un nouveau magasin de fichiers**, entrez le **Nom de domaine complet du serveur de fichiers** et le **Partage de fichiers**, puis cliquez sur **Suivant**.
    
     > [!NOTE]
     > Le partage de fichiers pour Skype entreprise Server peut être colocalisé, mais déconseillé pour des raisons de performances. Notez que, dans cet exemple, le partage de fichiers se situait sur un seul serveur dédié servant de partage de fichiers. Cependant, d’autres systèmes de partage de fichiers plus robustes, comme DFS sur Windows Server 2012 R2, sont recommandées. Pour plus d’informations sur les systèmes de partage de fichiers pris en charge, voir [Configuration requise pour votre environnement Skype entreprise](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). Pour plus d’informations sur la création du partage de fichiers, voir [créer un partage de fichiers dans Skype entreprise Server](create-a-file-share.md). Vous pouvez définir le partage de fichiers sans avoir à le créer. Vous devrez créer le partage de fichiers à l’emplacement défini avant de publier la topologie. 
  
10. Sur la page Spécifier l’URL des services Web, vous devez décider si vous avez besoin de remplacer l’URL interne du pool des services Web. La raison de ce remplacement est liée à l’équilibrage de la charge. Le trafic SIP de base peut être équilibré via un équilibrage DNS simple. Cependant, le trafic du réseau de services Web HTTP/S doit utiliser une solution d’équilibrage de la charge sur un logiciel ou un matériel. Pour les équilibreurs de charge pris en charge, voir [infrastructure pour Skype entreprise](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). Dans cet exemple, nous avons utilisé l’équilibrage DNS pour le trafic SIP et une solution d’équilibrage de la charge sur un logiciel. Étant donné que nous divisons le trafic de cette manière, nous devons remplacer le nom de domaine complet (FQDN) du pool des services Web internes. Si nous avions eu un équilibreur de charge de ligne supérieure et si nous avions envoyé tout le trafic par ce biais au lieu d’utiliser un équilibrage de charge DNS pour le trafic SIP, nous n’aurions pas eu besoin de remplacer l’URL des services Web. 
    
    Dans la section DNS de cette rubrique, nous avons créé un enregistrement A pour webint. contoso. local. Il s’agit de l’URL que nous utilisons pour le trafic HTTP/S de services Web, et il doit suivre l’équilibrage de charge logiciel pris en charge. Par conséquent, dans cet exemple, nous remplaçons l’URL pour laisser Skype entreprise Server savoir que le trafic HTTP/S doit être placé sur webint. contoso. local au lieu de pool. contoso. local, comme indiqué dans l’illustration. Pour en savoir plus sur l’équilibrage de charge, consultez la section [exigences d’équilibrage de charge pour Skype entreprise](../../plan-your-deployment/network-requirements/load-balancing.md).
    
    > [!IMPORTANT]
    > L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est https://webint.contoso.local, l’URL de base est webint. contoso. local. 
  
    - Si vous configurez l’équilibrage de la charge DNS, comme nous l’avons fait dans cet exemple, cochez la case **Remplacer le nom de domaine complet du pool des services web internes** et entrez l’URL de base interne (qui doit être différente du nom de domaine complet du pool) dans **URL de base interne**. 
    
    > [!CAUTION]
    > Si vous choisissez de remplacer le nom des services web internes par un nom de domaine complet personnalisé, chaque nom de domaine complet doit être différent de tout autre pool frontal, directeur ou pool directeur. **Utilisez uniquement les caractères standard** (y compris a-z, a-z, 0-9 et les traits d’Union) lorsque vous définissez des URL ou des noms de domaine complets. N’utilisez ni caractère Unicode ni trait de soulignement. En général, les DNS externes et les autorités de certification publiques ne prennent pas en charge les caractères non standard dans les URL ou noms de domaine complets (c’est-à-dire lorsque l’URL ou le nom de domaine complet doit être affecté au nom d’objet ou autre nom d’objet du certificat).
  
    - Vous pouvez aussi entrer l’URL de base externe dans **URL de base externe**. Entrez l’URL de base externe pour la différencier de votre nom de domaine interne. Par exemple, votre domaine interne est contoso.local, mais votre nom de domaine externe est contoso.com. Définissez alors l’URL à l’aide du nom de domaine contoso.com puisque cela peut être résolu à partir d’un DNS public. Cela est également important dans le cas d’un proxy inverse. Le nom de domaine de l’URL de base externe est le même que le nom de domaine du nom de domaine complet du proxy inverse. L’accès HTTP au pool frontal est requis pour la messagerie instantanée et la présence des clients Mobile.
    
      ![Remplacez les services web.](../../media/8f95313c-2df4-4885-adc5-9fc9ea775406.png)
  
11. Si vous sélectionnez **Conférence** dans la page **Sélectionner les fonctionnalités**, vous devrez ensuite sélectionner un serveur Office Web Apps. Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.
    
12. Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps**, tapez le nom de domaine complet de votre serveur Office Web Apps dans la zone **Nom de domaine complet du serveur Office Web Apps**. L’URL de découverte du serveur Office Web Apps est alors automatiquement entrée dans la zone **URL de découverte du serveur Office Web Apps**.
    
    Si Office Web Apps Server est installé en local et dans la même zone réseau que Skype entreprise Server, ne sélectionnez pas l’option le déploiement d' **Office Web Apps Server sur un réseau externe (par exemple, périmètre/Internet)**.
    
    Si le serveur Office Web Apps Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez alors l’option **Le serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)**.
    
13. Cliquez sur **Terminer** pour terminer la configuration. Si vous avez défini d’autres rôles serveur sur la page **Rôles serveur associés à ce pool frontal**, différentes pages de l’assistant de configuration de rôle s’ouvriront afin que vous puissiez configurer les rôles serveur. Dans cet exemple, nous avons choisi la conférence uniquement.
    
### <a name="configure-simple-urls"></a>Configurer des URL simples

1. Dans le générateur de topologie, cliquez avec le bouton droit sur le nœud supérieur **de Skype entreprise Server** , puis cliquez sur **modifier les propriétés**, comme indiqué dans l’illustration.
    
     ![Cliquez sur Skype Entreprise Server avec le bouton droit de la souris et sélectionnez Modifier les propriétés.](../../media/692c18dd-8e99-4239-ae7b-5e855d866afa.png)
  
2. Dans le volet **URL simples**, sélectionnez **URL d’accès téléphonique :** (Dial-In) ou **URL de réunion :** (Meet) pour modifier l’URL, puis cliquez sur **Modifier l’URL**.
    
3. Mettez à jour l’URL comme vous le souhaitez puis cliquez sur **OK** pour enregistrer l’URL modifiée. Vous devriez configurer l’URL simple en utilisant le domaine SIP externe pour que les utilisateurs externes puissent rejoindre des réunions, par exemple, contoso.com est un domaine externe, contrairement à contoso.local, qui est un domaine interne. Par conséquent, le domaine SIP doit être résolu par DNS externe.
    
4. Modifiez l’URL Meet en procédant de la même manière, si nécessaire.
    
### <a name="to-define-the-optional-admin-simple-url"></a>Pour définir l’URL simple Admin facultative

1. Dans le générateur de topologie, cliquez avec le bouton droit sur le nœud du **serveur Skype entreprise** , puis cliquez sur **modifier les propriétés**.
    
2. Dans la zone **URL d’accès administratif** , entrez l’URL de votre choix pour l’accès administratif au panneau de configuration Skype entreprise Server, puis cliquez sur **OK**.
    
    > [!TIP]
    > Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL d’administration. L’option la plus simple https://adminest. _Domain (domaine\>). \<_ L’URL d’administration peut être un domaine interne ou externe, par exemple contoso.local ou contoso.com, tant que les enregistrements peuvent être résolus dans un DNS interne. 
  
    > [!IMPORTANT]
    > Si vous changez une URL simple après son déploiement initial, vous devez savoir quels changements impactent vos enregistrements et certificats DNS pour les URL simples. Si le changement a un impact sur la base d’une URL simple, vous devez également modifier les enregistrements DNS et les certificats. Par exemple, si vous https://sfb.contoso.com/Meet modifiez https://meet.contoso.com l’URL de base de SFB.contoso.com à Meet.contoso.com, vous devez modifier les enregistrements DNS et les certificats pour faire référence à Meet.contoso.com. Si vous avez changé l’URL simple https://sfb.contoso.com/Meet de https://sfb.contoso.com/Meetingsà, l’url de base de SFB.contoso.com reste inchangée et aucune modification du DNS ou du certificat n’est nécessaire. Quand vous changez le nom d’une URL simple, vous devez par contre exécuter l’applet de commande **Enable-CsComputer** sur chaque pool directeur et frontal pour enregistrer le changement.
  
### <a name="publish-and-verify-the-topology"></a>Publier et vérifier la topologie

1. Vérifiez que toutes les URL simples sont configurées correctement.
    
2. Vérifiez que le serveur SQL Server est en ligne et que l’ordinateur sur lequel le Générateur de topologies est installé peut y accéder. Vérifiez également que les règles de pare-feu nécessaires sont disponibles.
    
3. Vérifiez que le partage de fichiers est disponible et qu’il dispose des autorisations appropriées qui ont été définies.
    
4. Confirmez que les rôles serveur corrects qui répondent à la configuration requise pour le déploiement sont définis dans la topologie.
    
5. Vérifiez que les serveurs existent sur les services de domaine Active Directory. Cela se produit automatiquement lorsque vous reliez les serveurs au domaine.
    
    Lorsque vous avez vérifié la topologie et qu’aucune erreur de validation n’a été détectée, vous êtes prêt à publier la topologie. Si des erreurs de validation sont détectées, vous devez les corriger pour publier la topologie.
    
6. Cliquez avec le bouton droit sur le nœud du **serveur Skype entreprise** , puis cliquez sur **publier la topologie**.
    
7. Dans la page **Publier la topologie**, cliquez sur **Suivant**.
    
8. Dans la page **Sélectionner un serveur de gestion centralisée**, sélectionnez un pool frontal, comme mentionné dans le schéma.
    
    > [!NOTE]
    > Vous pouvez cliquer sur **Avancé** pour configurer des emplacements de fichiers de bases de données.
  
     ![Sélectionnez le serveur du magasin central de gestion.](../../media/764478b5-8480-42c5-854f-649bb121cd94.png)
  
9. Dans la page **Sélectionner des bases de données**, sélectionnez les bases de données à publier.
    
    > [!NOTE]
    > Si vous ne disposez pas des autorisations appropriées pour créer les bases de données, désactivez les cases à cocher en regard de ces bases de données, et une personne disposant de droits appropriés peut créer les bases de données. Pour plus d’informations sur la configuration requise, voir [Configuration requise pour le serveur Skype entreprise Server](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  
10. Vous pouvez cliquer sur **Avancé**. Choisissez une option de sélection de l’emplacement des fichiers de données Advanced SQL Server parmi les suivantes : 
    
    - **Déterminez automatiquement l’emplacement du fichier de base de données** : cette option détermine les meilleures performances opérationnelles en fonction de la configuration du disque sur votre serveur SQL Server en répartissant les fichiers journaux et de données vers le meilleur emplacement.
    
    - **Utiliser les valeurs par défaut d’instances SQL Server** -cette option permet d’utiliser les fichiers de journaux et de données sur le serveur SQL Server en utilisant les paramètres d’instance. Cette option n’utilise pas la fonctionnalité opérationnelle du serveur SQL Server pour déterminer les emplacements optimum pour les journaux et données. En règle générale, l’administrateur SQL Server a déplacé les fichiers journaux et les fichiers de données vers des emplacements appropriés pour les procédures serveur et de gestion de l’organisation SQL Server.
    
    Cliquez sur **OK**, puis sur **Suivant**. 
    
11. Vous pouvez cliquer sur **Avancé**. Choisissez une option de sélection de l’emplacement des fichiers de données Advanced SQL Server parmi les suivantes : 
    
    - **Déterminez automatiquement l’emplacement du fichier de base de données** : cette option détermine les meilleures performances opérationnelles en fonction de la configuration du disque sur votre serveur SQL Server en répartissant les fichiers journaux et de données vers le meilleur emplacement.
    
    - **Utiliser les valeurs par défaut d’instances SQL Server** -cette option permet d’utiliser les fichiers de journaux et de données sur le serveur SQL Server en utilisant les paramètres d’instance. Cette option n’utilise pas la fonctionnalité opérationnelle du serveur SQL Server pour déterminer les emplacements optimum pour les journaux et données. En règle générale, l’administrateur SQL Server a déplacé les fichiers journaux et les fichiers de données vers des emplacements appropriés pour les procédures serveur et de gestion de l’organisation SQL Server.
    
    Cliquez sur **OK**.
    
12. Cliquez sur **Suivant** pour terminer le processus de publication.
    
    > [!NOTE]
    > L’échec de la création des bases de données SQL Server est une erreur courante dans cette étape. Lorsque le processus échoue, un message d’erreur apparait, comme mentionné dans le schéma. La cause la plus probable est que l’utilisateur qui tente de créer la base de données ne dispose pas des permissions appropriées, ou le système SQL Server est injoignable en raison d’un pare-feu ou d’un autre problème lié au réseau. 
  
     ![Erreur lors de la création du magasin central de gestion.](../../media/558bd2e4-2721-422d-9986-df86f642e6a1.png)
  
13. Lorsque le processus de publication est terminé, un lien permettant d’ouvrir une liste de tâches supplémentaires apparait. Cliquez sur **Cliquez ici pour ouvrir la liste de tâches** pour voir les tâches supplémentaires, puis cliquez sur **Terminer**. 
    
    Le message « Terminé avec des avertissements » lors de la création de la base de données ne signifie pas qu’il y a eu une erreur. Le processus d’installation doit modifier les paramètres dans SQL Server pour que Skype entreprise Server fonctionne correctement. Lorsqu’un paramètre est changé dans SQL Server, il est enregistré en tant qu’avertissement pour que les administrateurs de SQL Server puissent comprendre ce qu’a impacté le processus d’installation. Si vous recevez un message d’avertissement, vous pouvez sélectionner l’enregistrement, puis cliquez sur **afficher les journaux** pour afficher les détails de l’avertissement.
    
    Lorsque la topologie a été correctement publiée, vous pouvez commencer à installer une réplique locale du magasin de gestion central sur chaque serveur exécutant Skype entreprise Server dans votre topologie. Il est recommandé de commencer par le premier pool frontal. 
    

