First you need to run setup.exe, then you'll find the application as Tasker.exe.

The local admin for the application is:
  - USERNAME: localadm
  - PASSWORD: password

You need to configure an SQL Server for this app to function.

- Create a database called whatever you wish but replace in Queries the DatabaseName. Then copy paste the following queries, execute them for every "-".
    - USE [YOURDATABASE]
      GO

      /****** Object:  Table [dbo].[logs]    Script Date: 9/1/2023 10:34:04 AM ******/
      SET ANSI_NULLS ON
      GO

      SET QUOTED_IDENTIFIER ON
      GO

      CREATE TABLE [dbo].[logs](
	      [id] [int] NOT NULL,
	      [username] [nvarchar](max) NULL,
	      [roleid] [int] NULL,
	      [description] [nvarchar](max) NULL,
	      [time] [nvarchar](max) NULL
      ) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
      GO
      
  - USE [YOURDATABASE]
    GO

    /****** Object:  Table [dbo].[task_description]    Script Date: 9/1/2023 10:36:10 AM ******/
    SET ANSI_NULLS ON
    GO

    SET QUOTED_IDENTIFIER ON
    GO

    CREATE TABLE [dbo].[task_description](
	    [id] [int] NOT NULL,
	    [task_title] [nvarchar](max) NULL,
      [task_description] [nvarchar](max) NULL,
	    [task_application] [nvarchar](max) NULL,
	    [task_due] [nvarchar](max) NULL,
	    [task_status] [nvarchar](max) NULL
    ) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
    GO
    
  - USE [YOURDATABASE]
    GO

    /****** Object:  Table [dbo].[tasks_list]    Script Date: 9/1/2023 10:37:54 AM ******/
    SET ANSI_NULLS ON
    GO

    SET QUOTED_IDENTIFIER ON
    GO

    CREATE TABLE [dbo].[tasks_list](
	    [id] [int] NOT NULL,
	    [title] [nvarchar](max) NULL,
	    [application] [nvarchar](max) NULL,
	    [status] [nvarchar](max) NULL,
	    [due] [nvarchar](max) NULL
    ) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
    GO
    
  - USE [YOURDATABASE]
    GO

    /****** Object:  Table [dbo].[users]    Script Date: 9/1/2023 10:38:58 AM ******/
    SET ANSI_NULLS ON
    GO

    SET QUOTED_IDENTIFIER ON
    GO

    CREATE TABLE [dbo].[users](
	    [id] [int] IDENTITY(1,1) NOT NULL,
	    [username] [varchar](50) NULL,
    	[password] [varchar](50) NULL,
    	[role] [int] NULL,
    PRIMARY KEY CLUSTERED 
    (
	    [id] ASC
    )WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
    ) ON [PRIMARY]
    GO
