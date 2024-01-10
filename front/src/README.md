上に出すメニュー案
-1
  ```
  import * as React from 'react';
  import AppBar from '@mui/material/AppBar';
  import CssBaseline from '@mui/material/CssBaseline';
  import GlobalStyles from '@mui/material/GlobalStyles';
  import Toolbar from '@mui/material/Toolbar';
  import IconButton from '@mui/material/IconButton';
  import MenuIcon from '@mui/icons-material/Menu';
  import Typography from '@mui/material/Typography';
  
  export default function FabIntegrationSnackbar() {
    return (
      <React.Fragment>
        <CssBaseline />
        <GlobalStyles
          styles={(theme) => ({
            body: { backgroundColor: theme.palette.background.paper },
          })}
        />
        <div>
          <AppBar position="static" color="primary">
            <Toolbar>
              <IconButton
                edge="start"
                sx={{ mr: 2 }}
                color="inherit"
                aria-label="menu"
              >
                <MenuIcon />
              </IconButton>
              <Typography variant="h6" color="inherit" component="div">
                App bar
              </Typography>
            </Toolbar>
          </AppBar>
        </div>
      </React.Fragment>
    );
  }
  
  ```
-2
```
import * as React from 'react';
import AppBar from '@mui/material/AppBar';
import CssBaseline from '@mui/material/CssBaseline';
import GlobalStyles from '@mui/material/GlobalStyles';
import Toolbar from '@mui/material/Toolbar';
import IconButton from '@mui/material/IconButton';
import MenuIcon from '@mui/icons-material/Menu';
import Typography from '@mui/material/Typography';

export default function FabIntegrationSnackbar() {
  return (
    <React.Fragment>
      <CssBaseline />
      <GlobalStyles
        styles={(theme) => ({
          body: { backgroundColor: theme.palette.background.paper },
        })}
      />
      <div>
        <AppBar position="static" color="primary">
          <Toolbar>
            <IconButton
              edge="start"
              sx={{ mr: 2 }}
              color="inherit"
              aria-label="menu"
            >
              <MenuIcon />
            </IconButton>
            <Typography variant="h6" color="inherit" component="div">
              App bar
            </Typography>
          </Toolbar>
        </AppBar>
      </div>
    </React.Fragment>
  );
}

```
