---
title: "Ut. de la fonctionnalité Appelle-moi à avec un tél. prenant en charge Lync"
TOCtitle: "Ut. de la fonctionnalité Appelle-moi à avec un tél. prenant en charge Lync"
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56559395
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation de la fonctionnalité Appelle-moi à avec un téléphone prenant en charge Lync

 

_**Dernière rubrique modifiée :** 2013-08-09_

La fonctionnalité Appelle-moi à dans Lync permet aux utilisateurs de rejoindre la partie audio d’une conférence à l’aide d’un téléphone portable, d’un téléphone fixe ou d’un autre appareil connecté au réseau téléphonique commuté. Lorsque vous tentez de rejoindre une réunion à l’aide de Lync, la boîte de dialogue **Accéder à la partie audio de la réunion** s’affiche généralement :

![Capture d’écran de la fenêtre Utiliser Lync pour rejoindre une réunion audio](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Capture d’écran de la fenêtre Utiliser Lync pour rejoindre une réunion audio")

Si vous sélectionnez l’option **Appelle-moi à**, vous pouvez ensuite sélectionner un numéro de téléphone dans la liste déroulante. Lync Server 2013 passe un appel téléphonique au numéro sélectionné. Vous pouvez ensuite utiliser ce téléphone pour participer à la partie audio de la conférence.

La liste déroulante inclut les numéros de téléphone (téléphone mobile, téléphone personnel ou autre) que vous avez entrés sous l’onglet **Téléphones** de la boîte de dialogue **Lync – Options** :

![Capture d’écran des options de configuration des téléphones Lync](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Capture d’écran des options de configuration des téléphones Lync")

Si vous n’avez pas entré de numéro de téléphone sous l’onglet **Téléphones**, aucun numéro n’apparaît dans la liste déroulante. Vous pouvez tout de même cliquer sur **Nouveau numéro** et demander à Lync Server d’appeler le numéro de téléphone de votre choix :

![Capture d’écran de la fenêtre M’appeler pour participer à une réunion audio Lync](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Capture d’écran de la fenêtre M’appeler pour participer à une réunion audio Lync")

La fonctionnalité Appelle-moi à fonctionne correctement dès lors que vous l’utilisez correctement : en demandant à Lync Server d’appeler un numéro de téléphone PSTN. Vous pouvez toutefois rencontrer une expérience non optimale si vous demandez à Lync Server de vous appeler sur un point de terminaison activé pour Lync (par exemple, un téléphone dans une salle de conférence). Voici le problème que vous pouvez rencontrer, ainsi que deux façons de le contourner.

Pour commencer, voici ce qui arrive lorsque vous fournissez à la fonctionnalité Appelle-moi à le numéro d’un téléphone prenant en charge Lync. Supposons que Ken Myer essaie de rejoindre une réunion en demandant à Lync Server de l’appeler au 01 20 65 55 12, un numéro prenant en charge Lync Server. Ken est d’abord connecté à la réunion, mais après quelques secondes, Lync affiche le message **L’appel n’a pas été établi ou a pris fin**. Ken apparaît alors comme ayant quitté la réunion :

![Capture d’écran de la fenêtre de téléconférences Lync](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Capture d’écran de la fenêtre de téléconférences Lync")

Notez la présence d’une incohérence dans la fenêtre de conversation Lync. Ken Myer est le seul nom indiqué sous le titre **Participants**. Pourtant, si vous consultez la barre de titre de la fenêtre, vous verrez que la conférence réunit 4 participants.

De même, si vous consultez la fenêtre de conversation de l’un des participants à la conférence, Ken Myer n’apparaît nulle part :

![Capture d’écran de la fenêtre Liste des participants Lync](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Capture d’écran de la fenêtre Liste des participants Lync")

Pourtant, au même moment, Ken Myer peut participer à la partie audio de l’appel à l’aide de son téléphone prenant en charge Lync. La fonctionnalité Appelle-moi à a fonctionné correctement, mais l’expérience n’est pas optimale.

Il y a au moins deux façons de résoudre le problème. Si vous avez déjà rejoint une conférence de cette façon (comme Ken Myer), vous pouvez résoudre le problème en optant pour une autre modalité. Par exemple, si vous envoyez un message instantané, la fenêtre de conversation n’indique pas tous les participants à la conférence, y compris vous :

![Capture d’écran de la liste des participants et des conversations Lync](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Capture d’écran de la liste des participants et des conversations Lync")

À ce stade, vous devez pouvoir participer à la réunion comme prévu.

Vous pouvez aussi éviter ce problème en modifiant la façon dont vous rejoignez la réunion. Si vous avez besoin que Lync Server appelle un téléphone prenant en charge Lync Server, vous devez commencer par rejoindre la réunion sans connexion audio. Pour ce faire, sélectionnez l’option Ne pas participer au système dans la boîte de dialogue Acccéder à la partie audio de la réunion :

![Capture d’écran de la fenêtre Ne pas participer à une réunion audio Lync](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Capture d’écran de la fenêtre Ne pas participer à une réunion audio Lync")

Une fois que vous êtes connecté à la réunion, vous pouvez « inviter » le téléphone prenant en charge Lync Server pour rejoindre la réunion également. Pour ce faire, placez la souris sur l’icône Personnes, puis cliquez sur **Inviter d’autres personnes** :

![Capture d’écran de la fenêtre Inviter plus de participants Lync](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Capture d’écran de la fenêtre Inviter plus de participants Lync")

La boîte de dialogue **Envoyer un message instantané** s’ouvre. Ignorez le titre de la boîte de dialogue (vous n’allez pas vraiment envoyer un message instantané), puis tapez le numéro du téléphone prenant en charge Lync :

![Capture d’écran de la boîte de dialogue Envoyer un message instantané](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Capture d’écran de la boîte de dialogue Envoyer un message instantané")

Une fois que vous cliquez sur **OK**, Lync Server appelle le numéro entré dans la boîte de dialogue. Une fois la connexion établie, vous bénéficiez de fonctionnalités audio complètes via le téléphone prenant en charge Lync et vous pouvez afficher la liste de conférence et interagir avec.

